# EMPRESAS (CGM&A)

Portal EMPRESAS de CGM&A (empresa uruguaya de recuperación de activos): recopila la información relevante de cada empresa (manuales, pautas de carga, pautas administrativas e información comercial).
Responsable: Camila (área comercial). Idioma: español rioplatense, trato de "vos".

## Qué es
Un único archivo HTML que funciona sin instalar nada (doble clic, se abre en Edge o Chrome).
Se comparte copiando la carpeta completa a una carpeta compartida; las rutas son relativas.

- `Inicio CGM&A.html` — el portal. Todo (estilos, datos, lógica y el logo en base64) está en este archivo.
- `_plantilla/` — molde para crear el manual de una empresa nueva.
- `cobranza/<unidad>/<empresa>/` — carpeta de cada empresa. `cobranza/cesiones/mercurius/` lleva el paquete
  original "Manual Cesiones" (Construir manual.bat + build/), que es el modelo de referencia.
- `ventas/`, `otros/` — áreas todavía sin contenido ("Próximamente").

## Navegación (3 niveles, por hash de URL)
- `#inicio` → tarjetas de áreas: COBRANZA, VENTAS, OTROS (Ventas y Otros atenuadas, "Próximamente").
- `#cobranza` → tarjetas de unidades: TARDÍA, MT, AGUERREBERE, CESIONES, PERÚ.
- `#cobranza-cesiones` → empresas de la unidad.
- `#cobranza-cesiones-mercurius` → página de la empresa: migas de pan, ficha del equipo + índice a la
  izquierda, sección seleccionada a la derecha, botones anterior/siguiente.
Los tokens del hash se separan con guiones (no usar "/").

## Partes editables (dentro del <script> de Inicio CGM&A.html)
1. `ESTRUCTURA` — áreas > unidades > empresas.
   Empresa: `{ id, nombre, equipo, referente, lider, manual?, bajada? }`. Si falta equipo/referente/líder
   se muestra "A definir". Unidad: `{ id, nombre (MAYÚSCULAS), titulo (para la ficha), empresas:[] }`.
2. `PLANTILLA` — índice común a TODAS las empresas (`{EMPRESA}` se reemplaza por el nombre).
   Grupos con `proximamente:true` se muestran con etiqueta "Próximamente".
3. `CONTENIDO` — HTML de cada sección por empresa: `CONTENIDO["mercurius"]["1.1"] = "<p>…</p>"`.
   Si una sección no tiene texto se muestra el recuadro "Aquí va el contenido…".

## Índice acordado (glosario base, tomado de Mercurius)
1 · Manual: 1.1 Quién es {EMPRESA} · 1.2 Productos · 1.3 Montos a cobrar · 1.4 Pautas de gestión ·
    1.5 Medios de pago · 1.6 Promos vigentes · 1.7 Tablas
2 · Parámetros de carga: 2.1 Capital · 2.2 Máxima · 2.3 Mínima
3 · Pautas de asignación (próximamente a completar)
4 · Pautas administrativas (próximamente a completar)

## Ficha del equipo (recuadro sobre el índice)
Unidad · Equipo · Referente operativo · Líder operativo. Sin cotizaciones del dólar (se quitaron a pedido).
Mercurius: Unidad Cesiones · Equipo Mercurius · Referente Jean Franco Umpierrez · Líder Mónica Rocha.

## Empresas cargadas
- CESIONES: Mercurius (modelo), Fabraler (datos de ficha a definir).
- TARDÍA, MT, AGUERREBERE, PERÚ: pendiente el listado de empresas.

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
