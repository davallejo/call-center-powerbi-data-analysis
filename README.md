# 📊 Dashboard Call Center 2024
**Power BI** 📈 + **Power Query** 🔄 + **Excel** 📋

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=for-the-badge&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Windows](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)

Sistema de visualización y análisis operativo para la gestión de atención al cliente, construido sobre un modelo de datos limpio y transformado con ETL avanzado en Power Query.

**Generación de datos → Limpieza ETL → Modelado → Dashboard interactivo**

Elaborado por: Diego Vallejo

---

## 🎯 ¿De qué trata este proyecto?

Un call center recibe cientos de llamadas al día. Medir la calidad del servicio sin una herramienta visual es ineficiente y propenso a errores. Este proyecto simula exactamente ese escenario:

- 📋 **2.000 registros** de atenciones del mes de marzo son procesados desde Excel
- 🔄 **Power Query** limpia, normaliza y estandariza los datos automáticamente
- 📐 **El modelo** consolida todo en una única tabla liviana y optimizada
- 📊 **El Dashboard** segmenta por agente, área y temporalidad en tiempo real
- 🚨 **Los supervisores** detectan problemas de satisfacción y tiempo de respuesta de un vistazo

---

## 🧠 ¿Por qué Power BI? ¿Por qué este enfoque de modelo único?

### 📈 Power BI — La herramienta que lo hace posible

| Característica | Excel con Tablas | Power BI Desktop |
|----------------|-----------------|-----------------|
| Actualización de datos | Manual, propenso a errores | Automática con un clic |
| Filtros cruzados | Inexistentes | Nativos en todos los visuales |
| Escalabilidad | Limitada por la RAM del archivo | Modelo comprimido y optimizado |
| Storytelling | Estático | Dinámico e interactivo |

> **¿Por qué no solo Excel?** Excel es una herramienta de análisis, no de presentación ejecutiva. Con 2.000+ registros y múltiples dimensiones (agente, área, fecha), los dashboards en Excel se vuelven lentos y difíciles de mantener. Power BI gestiona esto de forma nativa.

### 🗄️ Modelo Desnormalizado — La decisión de diseño

| Característica | Modelo Estrella (varias tablas) | Tabla Única Desnormalizada |
|----------------|--------------------------------|---------------------------|
| Complejidad | Alta (relaciones, claves foráneas) | Baja (sin joins) |
| Rendimiento | Óptimo para millones de filas | Óptimo para miles de filas |
| Mantenimiento | Requiere conocimiento de modelado | Sencillo de actualizar |
| Caso de uso | Data Warehouse empresarial | Reporte operativo mensual |

> **¿Por qué una sola tabla?** Con 2.000 registros mensuales, un modelo estrella añade complejidad innecesaria. Una tabla `Atenciones` bien transformada en Power Query entrega el mismo resultado con menor fricción y mayor rendimiento.

---

## 🏗️ Arquitectura del Sistema

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│  📋 FUENTE DE DATOS      🔄 POWER QUERY        📐 MODELO       │
│  ──────────────────      ────────────────       ────────        │
│  Excel con 2.000    →    ETL: limpieza,    →   Tabla única     │
│  registros de marzo      normalización         Atenciones       │
│                          y estandarización                      │
│                                                                 │
│         ↓                      ↓                    ↓          │
│                                                                 │
│  📊 DASHBOARD            🎯 KPIs             🔍 SEGMENTACIÓN   │
│  ─────────────           ──────              ───────────────   │
│  Visualización           Llamadas,           Por agente,       │
│  interactiva             NPS y               área y            │
│  "Call Center 2024"      tiempos             temporalidad      │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 🔍 Los 3 KPIs Críticos del Dashboard

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│  K1 📞 LLAMADAS TOTALES        Conteo total de atenciones       │
│                                del período seleccionado         │
│                                                                 │
│  K2 ⭐ SATISFACCIÓN (NPS)      Índice promedio de satisfacción  │
│                                del cliente por atención         │
│                                                                 │
│  K3 ⏱️  VELOCIDAD DE RESPUESTA  Tiempo promedio de atención     │
│                                en segundos por llamada          │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## ✨ Características Principales

- **Análisis Exploratorio de Datos (EDA):** Evaluación inicial de la calidad de los datos para identificar tendencias y anomalías antes de la carga al modelo.
- **Proceso ETL Avanzado:** Limpieza y estandarización mediante Power Query, incluyendo división de columnas complejas y normalización de categorías para un modelo liviano y eficiente.
- **Visualización Dinámica:** Gráficos interactivos de barras, treemaps y anillos con filtros cruzados automáticos entre visuales.
- **KPIs en Tiempo Real:** Monitoreo de llamadas totales, satisfacción promedio (NPS) y tiempos de espera con actualización inmediata al aplicar filtros.
- **Diseño UX/UI Personalizado:** Fondo de lienzo personalizado con tema visual corporativo para mejorar la legibilidad y la experiencia del usuario final.

---

## 📊 Visualizaciones Implementadas

| # | Tipo de Visual | Nombre en Dashboard | Descripción |
|---|---------------|---------------------|-------------|
| 1 | **Card (KPI)** | Llamadas Totales | Conteo total de atenciones en el período | 
| 2 | **Card (KPI)** | Satisfacción Promedio (NPS) | Índice NPS agregado del período |
| 3 | **Card (KPI)** | Velocidad de Respuesta (S) | Tiempo promedio de respuesta en segundos |
| 4 | **Gráfico de Anillo** | Estado de la Atención | Distribución entre llamadas resueltas y no resueltas |
| 5 | **Gráfico de Barras** | Llamada por Asistente | Volumen de atenciones por cada agente |
| 6 | **Treemap** | *(Distribución por Área)* | Proporción de llamadas por área/departamento |
| 7 | **Columnas Agrupadas** | *(Tendencia Temporal)* | Evolución de llamadas con jerarquía de fechas (Año → Trimestre → Mes → Día) |
| 8 | **Slicer** | Filtro por Fecha | Segmentación temporal interactiva del período analizado |

---

## 🗄️ Modelo de Datos

### Tabla Principal: `Atenciones`

```
┌──────────────────────────────────────────────────────────────────┐
│                         Atenciones                               │
├───────────────────────────────┬───────────┬──────────────────────┤
│ Campo                         │ Tipo      │ Descripción          │
├───────────────────────────────┼───────────┼──────────────────────┤
│ Id llamada                    │ Entero    │ Identificador único  │
│ Fecha                         │ Fecha     │ Fecha de la atención │
│ Asistente                     │ Texto     │ Nombre del agente    │
│ Área                          │ Texto     │ Departamento asignado│
│ Respondido                    │ Booleano  │ Caso resuelto (S/N)  │
│ Índice de satisfacción (NPS)  │ Decimal   │ Score NPS del cliente│
│ Velocidad de respuesta        │ Entero    │ Segundos de atención │
└───────────────────────────────┴───────────┴──────────────────────┘
```

### Ejemplo de Registro

```json
{
  "Id llamada":                   1042,
  "Fecha":                        "2024-03-15",
  "Asistente":                    "Ana Ríos",
  "Área":                         "Ventas",
  "Respondido":                   "Sí",
  "Índice de satisfacción (NPS)": 8.5,
  "Velocidad de respuesta":       42
}
```

---

## ⚡ Cómo funciona Power Query internamente

```
Excel (2.000 filas brutas)
       ↓
  Power Query Editor
       ↓
  ┌───────────────────────────────────────────────────────────┐
  │  Paso 1: Promoción de encabezados                         │
  │  Paso 2: Detección automática de tipos de datos           │
  │  Paso 3: División de columnas complejas                   │
  │  Paso 4: Normalización de categorías (Área, Respondido)   │
  │  Paso 5: Eliminación de duplicados y valores nulos        │
  │  Paso 6: Formato de fecha estandarizado                   │
  └───────────────────────────────────────────────────────────┘
       ↓
  Tabla Atenciones cargada al modelo Power BI
       ↓
  Visuales + Filtros cruzados → Dashboard interactivo
```

---

## 📂 Estructura del Proyecto

```
dashboard-callcenter-2024/
│
├── 📊 Dashboard_Inicial.pbix       ← Archivo principal Power BI
│                                     (modelo + ETL + visuales)
│
├── 📁 data/
│   └── base_atenciones_marzo.xlsx  ← Fuente de datos origen (2.000 registros)
│
└── 📄 README.md                    ← Este archivo
```

---

## 🚀 Cómo usar el Dashboard

**Paso 1 — Prerrequisitos**

Descargar e instalar **Power BI Desktop** (gratuito):
👉 https://www.microsoft.com/es-es/power-platform/products/power-bi/desktop

**Paso 2 — Abrir el proyecto**

```
1. Descargar Dashboard_Inicial.pbix desde este repositorio
2. Abrir el archivo con Power BI Desktop
3. Si solicita credenciales, seleccionar "Anónimo" para fuentes locales
```

**Paso 3 — Actualizar la fuente de datos (opcional)**

```
Inicio → Transformar datos → Configuración del origen de datos
→ Apuntar al archivo Excel en tu ruta local
→ Cerrar y aplicar
```

**Paso 4 — Interactuar con el Dashboard**

```
✅ Usar el Slicer de Fecha para filtrar el período deseado
✅ Clic en cualquier visual para aplicar filtros cruzados
✅ Hover sobre los gráficos para ver tooltips detallados
✅ Publicar en Power BI Service para compartir con el equipo
```
<img width="884" height="495" alt="image" src="https://github.com/user-attachments/assets/4b31450a-be3b-4036-90c8-c39cde663782" />

---

## 📊 Análisis de Datos

### 🔎 1. Visión General de KPIs

| Métrica | Valor |
|---------|-------|
| 📞 Total de llamadas | 2.000 |
| ⭐ NPS promedio | 2.98 / 10 |
| ⏱️ Tiempo promedio de respuesta | 62 segundos |
| ✅ Tasa de resolución | 50.55% (Sí) vs 49.45% (No) |

#### 🧠 Interpretación
El comportamiento general evidencia un **problema estructural en la operación del call center**: baja satisfacción del cliente, alta proporción de casos no resueltos y tiempos de atención elevados.

---

### ⚠️ 2. Satisfacción del Cliente (NPS)

- **NPS promedio: 2.98 / 10** — nivel críticamente bajo que indica una experiencia negativa para la mayoría de clientes.

**Posibles causas:**
- Casos no resueltos en la primera llamada
- Largos tiempos de espera
- Ineficiencia en la gestión de agentes

> 💡 **Insight clave:** Existe una fuerte relación entre la **baja tasa de resolución** y el **bajo NPS**.

---

### ⏱️ 3. Tiempo de Respuesta

- **Promedio: 62 segundos** — superior al estándar recomendado de 30–40 segundos.

**Posibles causas:**
- Asignación ineficiente de llamadas
- Procesos internos lentos
- Brechas en la capacitación del personal

> 💡 **Insight:** Un tiempo de respuesta elevado impacta directamente y de forma negativa en la satisfacción del cliente.

---

### 👤 4. Análisis por Agente

#### Volumen de llamadas por agente

| Agente | Llamadas |
|--------|----------|
| Sofía Ramírez | 328 |
| Juan Pérez | 301 |
| Ana Torres | 282 |
| Carlos Sánchez | 280 |
| María López | 280 |
| Pedro Herrera | 266 |
| Luis Gómez | 263 |

La distribución es relativamente equilibrada, con una diferencia máxima de ~65 llamadas entre el agente con mayor y menor volumen. Sin embargo, el volumen por sí solo no refleja el desempeño real.

> 💡 **Insight clave:** Es necesario profundizar en el **NPS por agente** y la **tasa de resolución por agente** para identificar el rendimiento individual real y diseñar planes de capacitación dirigidos.

---

### 🏢 5. Distribución por Área

| Área | Llamadas |
|------|----------|
| Ventas | 507 |
| Cancelaciones | 504 |
| Intercambios | 497 |
| Reclamos | 492 |

La distribución es muy uniforme: ningún área presenta saturación y la carga operativa está completamente balanceada.

> 💡 **Insight:** El problema no es la carga de trabajo, sino la **eficiencia en la atención** dentro de cada área.

---

### 📅 6. Tendencia Temporal

| Mes | Llamadas |
|-----|----------|
| Enero | 153 |
| Febrero | 163 |
| Marzo | 169 |
| Abril | 155 |
| Mayo | 169 |
| Junio | 160 |
| Julio | 165 |
| Agosto | 163 |
| Septiembre | 161 |
| Octubre | 183 |
| Noviembre | 178 |
| Diciembre | 181 |

El volumen operativo se mantiene estable durante el año con una variación leve, registrando un incremento notable en el último trimestre (Q4).

> 💡 **Insight:** Se recomienda preparar recursos adicionales para el último trimestre, que concentra los picos de mayor demanda.

---

### ✅ 7. Tasa de Resolución

| Estado | Cantidad | Porcentaje |
|--------|----------|------------|
| ✅ Resueltas | ~1.011 | 50.55% |
| ❌ No resueltas | ~989 | 49.45% |

Una distribución prácticamente 50/50 representa una **ineficiencia operativa significativa**, con impacto directo en recontactos, mayor carga operativa y mala experiencia del cliente.

> 🚨 **Insight clave:** La baja tasa de resolución en primera llamada (FCR) es el **principal problema del negocio** y el driver más importante del bajo NPS.

---

### 🔥 Conclusión General

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│  🔴 PROBLEMAS PRINCIPALES       🟡 ASPECTOS CONTROLADOS        │
│  ─────────────────────────      ────────────────────────        │
│  • Baja satisfacción (NPS)      • Distribución equilibrada     │
│  • Baja tasa de resolución        de llamadas por agente       │
│  • Tiempos de respuesta         • Estabilidad en el volumen    │
│    elevados                       operativo anual              │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 💡 Insights de Negocio

El dashboard permite a supervisores y gerentes generar hipótesis críticas:

- 📉 **NPS vs Tiempo de Respuesta:** Identificar si los tiempos de espera prolongados se correlacionan con baja satisfacción en áreas como Ventas e Intercambios.
- 👤 **Rendimiento por Agente:** Detectar qué asistentes concentran mayor volumen y cómo impacta en su NPS individual, para diseñar planes de capacitación dirigidos.
- 🏢 **Carga por Área:** Visualizar qué departamentos reciben más llamadas y redistribuir recursos de forma eficiente.
- 📅 **Patrones Temporales:** Identificar días y horarios de mayor demanda con la jerarquía de fechas interactiva.
- ✅ **Tasa de Resolución:** Monitorear el porcentaje de casos efectivamente resueltos vs pendientes en tiempo real.

---

## 🎯 Recomendaciones Estratégicas

### 1. 🏆 Mejorar First Call Resolution (FCR)
- Capacitación intensiva de agentes en resolución de casos
- Implementar una base de conocimiento accesible durante la llamada

### 2. ⚡ Reducir Tiempos de Atención
- Optimización y rediseño de procesos internos
- Automatización de consultas frecuentes mediante scripts guiados

### 3. 📊 Implementar Medición Avanzada
- NPS individual por agente
- Tasa de resolución desglosada por agente y área
- Tiempo promedio segmentado por tipo de llamada

### 4. 🤖 Automatización
- Implementación de chatbots para consultas de bajo valor
- IVR inteligente para enrutamiento optimizado de llamadas

---

## 🛠️ Stack Tecnológico

| Herramienta | Versión | Rol en el proyecto |
|-------------|---------|-------------------|
| 📈 **Power BI Desktop** | 2.116.884.0 | Modelado de datos y creación de visualizaciones |
| 🔄 **Power Query (M)** | — | Transformación ETL y automatización del flujo |
| 📋 **Microsoft Excel** | — | Fuente de datos origen (2.000 registros de marzo) |
| 🎨 **Tema CY23SU04** | Power BI 2023.04 | Tema visual corporativo base del reporte |
| 🪟 **Windows** | 10 / 11 | Sistema operativo compatible |

---

## 📈 Posibles Extensiones

- 🤖 **Modelo Predictivo:** Integrar con Python/R para predecir la satisfacción antes de cerrar el caso usando los datos históricos.
- 🌊 **Datos en Tiempo Real:** Conectar a una base de datos SQL o API en lugar de Excel estático para actualizaciones automáticas.
- 📧 **Alertas Automáticas:** Configurar Power Automate para notificar al supervisor cuando el NPS caiga por debajo de un umbral definido.
- 🗺️ **Análisis Geográfico:** Agregar dimensión geográfica si los datos incluyen ubicación del cliente o la sucursal.
- 📱 **Vista Mobile:** Optimizar el layout para la app móvil de Power BI y consumo en tablets.
- 🔐 **Row-Level Security (RLS):** Implementar seguridad por agente para que cada asistente visualice únicamente sus propias métricas.

---

## 🧰 Solución de Problemas Comunes

**❌ Error: No se puede abrir el archivo `.pbix`**
```
→ Asegúrate de tener Power BI Desktop instalado (no Power BI Report Builder)
→ Descarga la versión más reciente desde Microsoft Store o el sitio oficial
```

**❌ Error: No se encuentran los datos / fuente no disponible**
```
→ Inicio → Transformar datos → Configuración del origen de datos
→ Cambiar origen → Navegar hasta la ubicación del archivo Excel en tu equipo
```

**❌ Los visuales no responden a los filtros cruzados**
```
→ Verificar que las interacciones estén habilitadas:
   Formato → Editar interacciones → Activar filtro cruzado en cada visual
```

**❌ El archivo `.pbix` no se actualiza con nuevos datos del Excel**
```
→ Inicio → Actualizar
→ Si falla, verificar que el archivo Excel no esté abierto en otra ventana
→ Comprobar que la ruta del archivo origen no haya cambiado
```

---

> Construido con 📈 Power BI + 🔄 Power Query + 📋 Excel
>
> Para uso educativo y demostración de arquitecturas de visualización ejecutiva y análisis operativo
>
> Elaborado por: **Diego Vallejo**
