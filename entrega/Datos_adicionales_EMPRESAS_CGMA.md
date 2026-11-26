# EMPRESAS (CGM&A) · Datos adicionales

Complemento del documento **Estructura_EMPRESAS_CGMA.html**. Contiene los datos concretos que hoy tiene el prototipo.

- Prototipo navegable: https://claude.ai/artifact/NGJavukk4BTrpEN2Uh99Jh
- Repositorio (código, logos originales): https://github.com/CLAPAZ-web/ManualesCGM
- Archivo del prototipo: `Inicio CGM&A.html` (un solo archivo HTML)

## 1. Áreas, unidades y empresas

### COBRANZA

- id: `cobranza` · descripción: Gestión de cobro por unidad y por empresa cliente.
- texto de la pantalla: Unidades de gestión de cobro.

#### TARDÍA (id `tardia`, título en ficha: Tardía) · 19 empresas

| # | Empresa | id | Logo | Colores propios |
|---|---|---|---|---|
| 1 | ITAU | `itau` | Sí | Sí |
| 2 | BTG PACTUAL | `btgpactual` | Sí | Sí |
| 3 | PAIGO - PYM | `paigopym` | Sí | Sí |
| 4 | PAIGO | `paigo` | Sí | Sí |
| 5 | OCA | `oca` | Sí | Sí |
| 6 | CRÉDITOS DIRECTOS | `creditosdirectos` | Sí | Sí |
| 7 | CASH | `cash` | No | No (usa CGM&A) |
| 8 | PRONTO | `pronto` | No | No (usa CGM&A) |
| 9 | PASS CARD | `passcard` | No | No (usa CGM&A) |
| 10 | VERDE | `verde` | No | No (usa CGM&A) |
| 11 | REPÚBLICA MICROFINANZAS | `republicamicrofinanzas` | No | No (usa CGM&A) |
| 12 | FASTCRED | `fastcred` | No | No (usa CGM&A) |
| 13 | NATIVA | `nativa` | No | No (usa CGM&A) |
| 14 | FIN UY | `finuy` | No | No (usa CGM&A) |
| 15 | CRÉDITO AMIGO | `creditoamigo` | No | No (usa CGM&A) |
| 16 | ECOCREDIT | `ecocredit` | No | No (usa CGM&A) |
| 17 | CAFUCA | `cafuca` | No | No (usa CGM&A) |
| 18 | FLERICO - ITALCRED | `flericoitalcred` | No | No (usa CGM&A) |
| 19 | COPAC | `copac` | No | No (usa CGM&A) |

#### MT (id `mt`, título en ficha: MT) · 0 empresas

_Empresas pendientes de cargar._

#### AGUERREBERE (id `aguerrebere`, título en ficha: Aguerrebere) · 0 empresas

_Empresas pendientes de cargar._

#### CESIONES (id `cesiones`, título en ficha: Cesiones) · 2 empresas

| # | Empresa | id | Logo | Colores propios |
|---|---|---|---|---|
| 1 | Mercurius | `mercurius` | No | No (usa CGM&A) |
| 2 | Fabraler | `fabraler` | No | No (usa CGM&A) |

#### PERÚ (id `peru`, título en ficha: Perú) · 0 empresas

_Empresas pendientes de cargar._

### VENTAS (Próximamente)

- id: `ventas` · descripción: Manuales y pautas del área comercial.

### OTROS (Próximamente)

- id: `otros` · descripción: Procedimientos y material transversal.

## 2. Fichas del equipo con datos

Valores iniciales definidos en el prototipo (el resto figura como "A definir"):

- **Mercurius** · Unidad: Cesiones · Referente operativo: Jean Franco Umpierrez · Líder operativo: Mónica Rocha · Equipo: Mercurius · Asesores: A definir

Desde la página no se cargó todavía ninguna ficha adicional.

## 3. Índice común (secciones con su bajada)

### 1 · Manual

- **1.1 Quién es [Empresa]**: Presentación de la empresa y de las carteras que gestiona la unidad.
- **1.2 Productos**: Tipos de producto que gestiona la empresa y cómo identificarlos en la ficha del cliente.
- **1.3 Montos a cobrar**: Saldo, mínima y máxima: qué monto se le informa al cliente en cada caso.
- **1.4 Pautas de gestión**: Cómo se negocia según la cartera, la fecha de vencimiento y el tipo de deuda.
- **1.5 Medios de pago**: Dónde y cómo puede pagar el cliente, y qué código de pago informarle.
- **1.6 Promos vigentes**: Condiciones de las promociones activas: quitas, cantidad de cuotas y cuota mínima.
- **1.7 Tablas**: Tablas de refinanciación y cálculo de cuotas.

### 2 · Pautas de carga

- **2.1 Montos** **[formulario]**: Criterios para cargar el capital, la mínima, la máxima y el monto de promoción de cada operación.
- **2.2 Segmento, subcartera y etiquetas** **[formulario]**: Cómo se clasifica la operación: segmento, subcartera y etiquetas a aplicar.
- **2.3 Notas** **[formulario]**: Qué información se registra en las notas de la operación y de la deuda.

### 3 · Pautas de asignación

- **3.1 Pautas de asignación** **[formulario]**: Cómo envía la empresa la asignación de cuentas y qué reportes se le devuelven.

### 4 · Pautas administrativas (Próximamente)

- **4.1 Pautas administrativas**: Próximamente a completar.

### 5 · Comercial

- **5.1 Comisiones**: Comisiones acordadas con la empresa y cómo se calculan.
- **5.2 Contrato**: Condiciones del contrato vigente con la empresa.

## 4. Opciones de los desplegables (Pautas de asignación)

| Campo | Clave | Opciones |
|---|---|---|
| Tipo de asignación | `tipo` | Stock · Actualización · Stock y actualización · Sólo ingreso · Stock e ingreso |
| Frecuencia de envío | `frecuencia` | Diaria · Semanal · Quincenal · Mensual |
| ¿Se recibe actualización? | `recibeAct` | Sí · No |
| Frecuencia envío actualización | `frecuenciaAct` | Nunca · Diaria · Semanal · Quincenal |
| Reportería | `reporteria` | Lista libre (se agregan y quitan reportes) |

## 5. Pautas de asignación ya cargadas

- **BTG PACTUAL**: Tipo de asignación: Stock e ingreso · Frecuencia de envío: Mensual · ¿Se recibe actualización?: No · Frecuencia envío actualización: Nunca

## 6. Colores por empresa (tema)

Se aplican al entrar a la página de la empresa. Todos los temas actuales son de fondo claro.

| Empresa | cabecera | fondo | tarjeta | tarjeta2 | texto | suave | tenue | acento | sección activa | hover | línea | subrayado |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| ITAU | `#FF6200` | `#FFF7F0` | `#FFFFFF` | `#FFEFE2` | `#2A1A10` | `#6E5547` | `#9C8576` | `#C24A00` | `#FFE3CC` | `rgba(255,98,0,.08)` | `rgba(140,60,0,.16)` | `rgba(194,74,0,.5)` |
| BTG PACTUAL | `#001E61` | `#F3F5FA` | `#FFFFFF` | `#E8EDF7` | `#0B1633` | `#4A5677` | `#8590AB` | `#001E61` | `#DCE4F4` | `rgba(0,30,97,.06)` | `rgba(0,30,97,.14)` | `rgba(0,30,97,.45)` |
| PAIGO - PYM | `#6D29FA` | `#F7F4FF` | `#FFFFFF` | `#EFE9FF` | `#111111` | `#4F4A5E` | `#8C879A` | `#5B1FE0` | `#E6DCFF` | `rgba(109,41,250,.07)` | `rgba(60,20,140,.14)` | `rgba(109,41,250,.45)` |
| PAIGO | `#F9460F` | `#FFF6F2` | `#FFFFFF` | `#FFECE4` | `#2A140C` | `#6E5148` | `#9C837A` | `#C93A0C` | `#FFDCCD` | `rgba(249,70,15,.07)` | `rgba(150,50,10,.15)` | `rgba(201,58,12,.5)` |
| OCA | `#006ED2` | `#F2F7FD` | `#FFFFFF` | `#E6F0FB` | `#0B1E33` | `#4A5E75` | `#8798AC` | `#005BB0` | `#D6E6F8` | `rgba(0,110,210,.07)` | `rgba(0,60,120,.14)` | `rgba(0,91,176,.45)` |
| CRÉDITOS DIRECTOS | `#007D3A` | `#F4F9F1` | `#FFFFFF` | `#E6F2E4` | `#0F2318` | `#4B6255` | `#889A8E` | `#006B32` | `#FFF1A0` | `rgba(0,125,58,.07)` | `rgba(0,80,40,.15)` | `rgba(0,107,50,.45)` |

Base CGM&A (sin tema propio): fondo `#0b1f45`, tarjeta `#10285a`, tarjeta2 `#163266`, línea `rgba(196,210,240,.18)`, texto `#ffffff`, suave `#b9c6e2`, tenue `#7d8db0`, acento `#d9b66f`, sección activa `#2a4277`.

## 7. Logos

| Empresa | Archivo original en el repositorio |
|---|---|
| ITAU | `cobranza/tardia/itau/logo_itau.png` |
| BTG PACTUAL | `cobranza/tardia/btgpactual/logo_btgpactual.png` |
| PAIGO - PYM | `cobranza/tardia/paigopym/logo_paigopym.png` |
| PAIGO | `cobranza/tardia/paigo/logo_paigo.png` |
| OCA | `cobranza/tardia/oca/logo_oca.svg` |
| CRÉDITOS DIRECTOS | `cobranza/tardia/creditosdirectos/logo_creditosdirectos.png` |
| CGM&A (blanco) | `_plantilla/logo_cgma_blanco.png` |

## 8. Textos de la interfaz

- Cabecera: "Información de empresas" junto al logo CGM&A.
- Inicio: título "EMPRESAS" + "En este apartado se recopila toda la información relevante sobre las empresas de CGM&A: manuales, pautas de carga, pautas administrativas e información comercial. Elegí el área de trabajo para empezar."
- Unidad sin empresas: "Todavía no hay empresas cargadas en esta unidad."
- Página de empresa: "Unidad [UNIDAD] · Manual de gestión de la empresa, armado sobre la plantilla común."
- Sección vacía: "Aquí va el contenido de la sección adaptado a [Empresa]." · Grupo próximamente: "Esta sección se va a completar próximamente."
- Ficha vacía: "A definir". En cada campo: "+ Agregar" (cuadro "Nombre y apellido" + botón "Agregar") y × para quitar.
- Reportería vacía: "Sin reportes cargados." · Campo: "Agregar un reporte (ej. Reporte de gestión)".
- Estados de guardado: "Guardando…", "Guardado.", "No tenés permiso para editar estos datos.", "No se pudo guardar. Probá de nuevo."
- Pie: "EMPRESAS · CGM&A · Gestión de cobranza y contact center · Maqueta de estructura general: los contenidos se irán completando."

## 9. Notas técnicas del prototipo

- Navegación por la dirección de la página: `#inicio`, `#cobranza`, `#cobranza-tardia`, `#cobranza-tardia-itau` (niveles separados por guion; por eso los id no llevan guiones).
- Ficha, Montos, Segmento/subcartera/etiquetas, Notas y Pautas de asignación se guardan en una base de datos compartida, un registro por empresa: colección `ficha` (referente[], lider[], equipo[], asesores[]), `montos` (capital, minima, maxima, promocion), `clasificacion` (segmento, subcartera, etiquetas), `notas` (operacion, deuda) y `asignacion` (tipo, frecuencia, recibeAct, frecuenciaAct, reporteria[]).
- Los valores de la ficha definidos en el prototipo funcionan como valores iniciales; lo cargado desde la página los reemplaza.
- Las empresas sin `tema` usan los colores de CGM&A; las que tienen logo lo muestran como título de su página.
