# Proyecto 11: Análisis de Eventos y Comportamiento de Usuario
> **Optimización del Embudo de Conversión y Test A/B para Startup Alimenticia**

---

## 📝 Descripción del Proyecto
Este estudio investiga el comportamiento de los usuarios dentro de la aplicación móvil de una empresa de alimentos. El objetivo es comprender cómo interactúan los clientes con la interfaz y evaluar si los cambios en las fuentes de la aplicación afectan la tasa de conversión mediante experimentos controlados.

### 📋 Resumen de Datos
* **Total de Eventos:** 244,126 registros.
* **Total de Usuarios:** 7,551 individuos únicos.
* **Periodo de Análisis:** Del 1 al 7 de agosto de 2019 (tras limpieza de datos antiguos).
* **Grupos Experimentales:** * `246` y `247`: Grupos de Control (A).
    * `248`: Grupo de Prueba (B) con fuentes modificadas.

---

## 🌪️ Análisis del Embudo de Ventas (Funnel)

Al analizar la secuencia de eventos, se identificó un flujo estándar de compra. Sin embargo, el evento de **Tutorial** es ignorado por la mayoría, lo que sugiere que la aplicación es intuitiva o el acceso al tutorial no es atractivo.



### Métricas de Conversión por Etapa:
| Etapa | Evento | Usuarios Únicos | % de Retención |
| :--- | :--- | :--- | :--- |
| 1 | **MainScreenAppear** (Inicio) | 7,206 | 100% |
| 2 | **OffersScreenAppear** (Ofertas) | 4,414 | 61.2% |
| 3 | **CartScreenAppear** (Carrito) | 3,601 | 81.6% |
| 4 | **PaymentScreenSuccessful** (Pago) | 3,418 | 94.9% |

**Hallazgo Crítico:** La mayor pérdida de usuarios ocurre entre la **Pantalla Principal** y la de **Ofertas**, donde se pierde el **38.8%** de los prospectos. Una vez que el usuario llega al carrito, la probabilidad de éxito es altísima (94.9%).

> **Conversión Total:** Solo el **17.6%** de los usuarios completa el viaje desde el inicio hasta el pago.

---

## 🧪 Resultados del Experimento (A/A/B Test)

Se realizaron pruebas de hipótesis para comparar las proporciones de usuarios en cada evento entre los grupos.

### 1. Validación del Test A/A (Grupos 246 vs 247)
Para asegurar que la segmentación fue aleatoria y correcta, comparamos los grupos de control:
* **Resultado:** No se encontraron diferencias significativas ($p = 0.7032$).
* **Conclusión:** Los grupos son estadísticamente equivalentes; el mecanismo de división es fiable.

### 2. Test A/B (Grupo de Prueba 248)
Comparamos el grupo con fuentes alteradas (`248`) frente a los grupos de control combinados:
* **Evento más popular:** `MainScreenAppear`.
* **Resultado:** Todas las pruebas arrojaron valores $p$ superiores a **0.05**.
* **Conclusión:** El cambio de fuentes **no tuvo un impacto significativo** (ni positivo ni negativo) en el comportamiento de compra de los usuarios.

---

## 🛠️ Metodología Estadística
Para evitar el problema de comparaciones múltiples y el aumento de falsos positivos (Error Tipo I), se analizaron los niveles de significancia:

* **Nivel de significancia ($\alpha$):** 0.05.
* **Número de pruebas realizadas:** 20 pruebas estadísticas.
* **Ajuste sugerido:** Dado que realizamos 20 pruebas, el uso de la **Corrección de Bonferroni** sugeriría un $\alpha$ de **0.0025** para mantener la robustez del experimento. Sin embargo, incluso con el umbral original, los resultados se mantienen consistentes.

---

## 🔗 Entregables
* [📂 Ver Análisis de Eventos Completo (Jupyter Notebook)](https://github.com/LuisPeza/Proyecto_11/blob/main/Proyecto_11.ipynb)


