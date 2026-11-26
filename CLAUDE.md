# EMPRESAS (CGM&A)

Portal EMPRESAS de CGM&A (empresa uruguaya de gestión de cobranza y contact center): recopila la información relevante de cada empresa (manuales, pautas de carga, pautas administrativas e información comercial).
Responsable: Camila (área comercial). Idioma: español rioplatense, trato de "vos".

## Qué es
Un único archivo HTML que funciona sin instalar nada (doble clic, se abre en Edge o Chrome).
Se comparte copiando la carpeta completa a una carpeta compartida; las rutas son relativas.

- `Inicio CGM&A.html` — el portal. Todo (estilos, datos, lógica y el logo en base64) está en este archivo.
- `_plantilla/` — molde para crear el manual de una empresa nueva.
- `cobranza/<unidad>/<empresa>/` — carpeta de cada empresa. `cobranza/cesiones/mercurius/` lleva el paquete
  original "Manual Cesiones" (Construir manual.bat + build/), que es el modelo de referencia.
- `ventas/`, `otros/` — áreas todavía sin contenido ("Próximamente").
- `entrega/` — documento de traspaso para desarrollar el portal en otro sistema: `Estructura_EMPRESAS_CGMA.html`
  (estructura, pantallas, formularios, modelo de datos) + `Datos_adicionales_EMPRESAS_CGMA.md` (datos concretos).

## Navegación (3 niveles, por hash de URL)
- `#inicio` → tarjetas de áreas: COBRANZA, VENTAS, OTROS (Ventas y Otros atenuadas, "Próximamente").
- `#cobranza` → tarjetas de unidades: TARDÍA, MT, AGUERREBERE, CESIONES, PERÚ.
- `#cobranza-cesiones` → empresas de la unidad.
- `#cobranza-cesiones-mercurius` → página de la empresa: migas de pan, ficha del equipo + índice a la
  izquierda, sección seleccionada a la derecha, botones anterior/siguiente.
Los tokens del hash se separan con guiones (no usar "/").

## Partes editables (dentro del <script> de Inicio CGM&A.html)
1. `ESTRUCTURA` — áreas > unidades > empresas.
   Empresa: `{ id, nombre, equipo, referente, lider, asesores?:[], manual?, bajada? }`. Si falta equipo/referente/líder
   se muestra "A definir". Unidad: `{ id, nombre (MAYÚSCULAS), titulo (para la ficha), empresas:[] }`.
2. `PLANTILLA` — índice común a TODAS las empresas (`{EMPRESA}` se reemplaza por el nombre).
   Grupos con `proximamente:true` se muestran con etiqueta "Próximamente".
3. `CONTENIDO` — HTML de cada sección por empresa: `CONTENIDO["mercurius"]["1.1"] = "<p>…</p>"`.
   Si una sección no tiene texto se muestra el recuadro "Aquí va el contenido…".
4. `LOGOS` — logo de cada empresa en base64 (PNG ~192px): `LOGOS["itau"] = "data:image/png;base64,…"`.
   El original se guarda en la carpeta de la empresa (ej. cobranza/tardia/itau/logo_itau.png).
   El logo se ve en la tarjeta de la empresa y, en su página, reemplaza al nombre como título (sin logo se muestra el nombre).

## Colores por empresa
Cada empresa puede tener `tema:{…}` en ESTRUCTURA: al entrar a su página se pisan las variables CSS
(cabecera, cab-suave, cab-linea, fondo, tarjeta, tarjeta2, linea, texto, suave, tenue, oro, activo, hover,
subrayado; `esquema:"light"` para fondos claros). Al salir vuelven los colores de CGM&A.
ITAU: cabecera naranja #FF6200, fondo claro #FFF7F0, acento #C24A00.
BTG PACTUAL: cabecera azul #001E61, fondo claro #F3F5FA, acento #001E61.
PAIGO - PYM: cabecera violeta #6D29FA, fondo claro #F7F4FF, acento #5B1FE0.
PAIGO: cabecera naranja #F9460F, fondo claro #FFF6F2, acento #C93A0C.
OCA: cabecera azul #006ED2, fondo claro #F2F7FD, acento #005BB0 (original en SVG).
CRÉDITOS DIRECTOS: cabecera verde #007D3A, fondo claro #F4F9F1, acento #006B32, sección activa amarilla #FFF1A0.
En las tarjetas el logo va sobre un recuadro blanco (para que se vean logos oscuros sobre el azul de CGM&A).

## Índice acordado (glosario base, tomado de Mercurius)
1 · Manual: 1.1 Quién es {EMPRESA} · 1.2 Productos · 1.3 Montos a cobrar · 1.4 Pautas de gestión ·
    1.5 Medios de pago · 1.6 Promos vigentes · 1.7 Tablas
2 · Pautas de carga: 2.1 Montos (formulario: Capital, Mínima, Máxima, Monto promoción) · 2.2 Segmento, subcartera y etiquetas
    (formulario: Segmento, Subcartera, Etiquetas) · 2.3 Notas (formulario: Notas de la operación, Notas de la deuda)
3 · Pautas de asignación: 3.1 es un formulario (ver abajo)
4 · Pautas administrativas (próximamente a completar)
5 · Comercial: 5.1 Comisiones · 5.2 Contrato

## Formularios de texto (2.1 Montos, 2.2 Segmento, subcartera y etiquetas, 2.3 Notas)
Definidos en `FORMS_TEXTO` (clave = tipo = colección del db): `montos` (capital, minima, maxima, promocion) y `clasificacion`
(segmento, subcartera, etiquetas) y `notas` (operacion, deuda). En PLANTILLA el 4º elemento del ítem indica el tipo. Cuadros de texto libre
por empresa; se guarda solo al escribir (0,9 s de pausa), al salir del cuadro o al cambiar de sección.
Doc por id de empresa en la colección del tipo; localStorage `<tipo>_<id>` en la carpeta.

## Pautas de asignación (formulario en 3.1)
Desplegables definidos en `CAMPOS_ASIG` (parte editable 5): Tipo de asignación (Stock/Actualización/Stock y actualización/Sólo ingreso/Stock e ingreso),
Frecuencia de envío (Diaria/Semanal/Quincenal/Mensual), Canal de envío (MAIL/FTP/API/CONNECT/WEB SERVICES),
¿Se recibe actualización? (Sí/No),
Frecuencia envío actualización (Nunca/Diaria/Semanal/Quincenal) + Reportería (lista libre, se agregan/quitan reportes).
Guardado: en el link de claude.ai, base de datos del artifact (capability `db`, colección `asignacion`, un doc por
id de empresa), compartida para todos. Abierto desde la carpeta (file://), localStorage de ese navegador.

## Ficha del equipo (recuadro sobre el índice)
Cada campo (Referente, Líder, Equipo, Asesores) es una lista de personas: "+ Agregar" abre un cuadro para escribir
el nombre (Enter/Agregar, Escape cancela) y × quita. Se guarda solo, igual que la asignación: colección `ficha` del db (un doc por id de empresa) en claude.ai, localStorage en la carpeta.
Lo guardado pisa los valores de ESTRUCTURA, que quedan como valores iniciales.
Unidad · Referente operativo · Líder operativo · Equipo · Asesores (en ese orden; todos son listas, valores sueltos de ESTRUCTURA se leen como lista de uno). Sin cotizaciones del dólar (se quitaron a pedido).
Mercurius: Unidad Cesiones · Equipo Mercurius · Referente Jean Franco Umpierrez · Líder Mónica Rocha.

## Empresas cargadas
- CESIONES: Mercurius (modelo), Fabraler (datos de ficha a definir).
- TARDÍA (19): ITAU, BTG PACTUAL, PAIGO - PYM, PAIGO, OCA, CRÉDITOS DIRECTOS, CASH, PRONTO, PASS CARD,
  VERDE, REPÚBLICA MICROFINANZAS, FASTCRED, NATIVA, FIN UY, CRÉDITO AMIGO, ECOCREDIT, CAFUCA,
  FLERICO - ITALCRED, COPAC (fichas a definir). Los id no llevan guiones ni espacios (ej. paigopym).
- MT, AGUERREBERE, PERÚ: pendiente el listado de empresas.

## Diseño
Fondo azul marino (#0b1f45), tarjetas #10285a, acento dorado (#d9b66f), texto blanco.
Títulos en Libre Baskerville (fallback Georgia), texto en Inter (fallback Segoe UI).
Logo CGM&A en blanco con "&" gris, incrustado en base64 (original: _plantilla/logo_cgma_blanco.png).

## Pendientes
- Recibir el listado de empresas por unidad y cargarlo en ESTRUCTURA.
- Completar el contenido de Mercurius sección por sección (base en el manual original de Cesiones:
  buscador de pautas, tabla de refinanciación, medios de pago, etc.), y replicarlo en las demás empresas.

## Reglas
- No usar datos personales de clientes en capturas o ejemplos.
- Mantener todo en un solo HTML sin dependencias que requieran instalación.
