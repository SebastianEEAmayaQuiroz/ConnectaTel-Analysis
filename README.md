# ConnectaTel-Analysis
Análisis de comportamiento de clientes de telecomunicaciones - Proyecto ConnectaTel
# 📊 ConnectaTel - Análisis de Telecomunicaciones

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1-3xISuOlh75It6_VrF5e3pmrrp5aZ3qO?usp=drive_link)
[![Ver Reporte HTML](https://img.shields.io/badge/Ver-Reporte%20HTML-orange)](./S7%20Version-Estudiante-Project-ConnectaTel.html)

## 📌 Descripción del Proyecto

Análisis de comportamiento de clientes para **ConnectaTel**, empresa de telecomunicaciones con operaciones en México y Colombia.

**Objetivo:** Identificar patrones de uso, detectar comportamientos atípicos y comprender qué segmentos de clientes muestran necesidades diferenciadas para optimizar la oferta comercial y mejorar la experiencia del usuario.

---

## 📁 Datasets utilizados

| Dataset | Descripción | Filas | Columnas |
|---------|-------------|-------|----------|
| `plans.csv` | Catálogo de planes (precio, minutos, GB incluidos) | 2 | 8 |
| `users_latam.csv` | Información de clientes (edad, ciudad, plan, registro) | 4,000 | 8 |
| `usage.csv` | Detalle de uso real (llamadas y mensajes) | 40,000 | 6 |

---

## 🔧 Etapas del Análisis

1. **Carga y Exploración** - Estructura y tipos de datos
2. **Limpieza de Datos** - Valores nulos, sentinelas, fechas
3. **Análisis Estadístico** - Perfil de uso por usuario
4. **Visualización** - Histogramas, boxplots, distribuciones
5. **Detección de Outliers** - Método IQR
6. **Segmentación** - Por edad y nivel de uso
7. **Insights Ejecutivos** - Recomendaciones de negocio

---

## 📈 Principales Hallazgos

### Problemas detectados y corregidos
- `age`: 55 valores `-999` (1.38%) → imputados con mediana (48 años)
- `city`: 96 valores `"?"` + 469 NaN → reemplazados por "Desconocido"
- `reg_date`: 40 fechas futuras (2026) → eliminadas

### Segmentos identificados

| Segmento | Rango | Porcentaje | Comportamiento |
|----------|-------|------------|----------------|
| **Joven** | 18-29 años | 25% | Menor consumo, prefieren plan Básico |
| **Adulto** | 30-59 años | 43.7% | Core del negocio, consumo balanceado |
| **Adulto Mayor** | 60+ años | 31.3% | Alta propensión a Premium |

### Distribución por uso

| Nivel | Criterio | Porcentaje |
|-------|----------|------------|
| Bajo uso | llamadas <5 Y mensajes <5 | 25% |
| Uso medio | llamadas <10 Y mensajes <10 | 62.5% |
| Alto uso | Resto de casos | 37.5% |

### Outliers detectados

| Variable | Outliers | % | Implicación |
|----------|----------|---|-------------|
| Mensajes | 46 | 1.15% | Usuarios superactivos |
| Llamadas | 30 | 0.75% | Clientes de alto valor |
| Minutos | 109 | 2.73% | **Heavy users** (hasta 156 min) |

---

## 💡 Recomendaciones de Negocio

1. **Digital Youth** - Plan para jóvenes (18-29) con más GB y menos minutos
2. **VIP ConnectaTel** - Programa exclusivo para 109 outliers de alto consumo
3. **Upselling** - Migrar usuarios Básico en uso medio-alto a Premium
4. **Dashboard** - Monitoreo mensual de segmentos y outliers

---

## 📊 Tecnologías utilizadas

| Herramienta | Propósito |
|-------------|-----------|
| **Python 3.9** | Lenguaje principal |
| **Pandas** | Manipulación y limpieza de datos |
| **NumPy** | Operaciones numéricas |
| **Matplotlib & Seaborn** | Visualizaciones y gráficos |
| **Jupyter Notebook** | Entorno interactivo de desarrollo |

---

## 👤 Autor

**Análisis ConnectaTel** - Proyecto de análisis de datos para empresa de telecomunicaciones.

📅 *Proyecto completado - Abril 2026*

---

## 📝 Licencia

Este proyecto es de uso educativo y demostrativo.

---

## 🚀 Cómo ejecutar el notebook

### Opción 1: Google Colab (Recomendado)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1-3xISuOlh75It6_VrF5e3pmrrp5aZ3qO?usp=drive_link)

Haz clic en el badge de arriba para abrir directamente el notebook en Colab.

### Opción 2: 


### Opción 3: Local
```bash
# Clonar el repositorio
git clone https://github.com/SebastianEEAmayaQuiroz/ConnectaTel-Analysis.git

# Instalar dependencias
pip install pandas numpy seaborn matplotlib

# Abrir Jupyter Notebook
jupyter notebook "S7 Version-Estudiante-Project-ConnectaTel.ipynb"

