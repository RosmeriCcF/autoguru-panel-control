# 🚘 AutoGurú — Panel de control para Car Wash

Dashboard web responsive para el control diario de autos: cuántos carros entran, cuánto se factura, qué servicios se piden más y el historial de lavados por placa. 

## 🎯 Objetivo

Darle al dueño del negocio una forma simple de ver, desde su celular, la salud del negocio en tiempo real: ingresos, volumen de autos, medios de pago y el historial completo de cualquier cliente por placa — sin depender de abrir una hoja de cálculo.

## 🧱 Stack tecnológico

| Capa | Tecnología | Para qué se usó |
|---|---|---|
| Captura de datos | **Google Forms** | Formulario que llena el operador por cada lavado |
| Almacenamiento | **Google Sheets** | Base de datos (cada respuesta del Form cae ahí como fila) |
| Backend / API | **Google Apps Script** | Puente que lee el Sheet y lo expone como JSON vía una Web App |
| Frontend | **HTML5 + CSS3 + JavaScript** | Dashboard responsive, sin frameworks |
| Gráficos | **Chart.js** + **chartjs-plugin-datalabels** | Visualización de ingresos, servicios, medios de pago, etc. |
| Hosting | **GitHub Pages** | Publicación del sitio estático |
| Control de versiones | **Git / GitHub** | Historial de cambios y despliegue |

## ⚙️ Cómo funciona (arquitectura)

```
Google Form  →  Google Sheet  →  Apps Script (Code.gs)  →  JSON  →  index.html (fetch)
   (input)         (BD)              (API/puente)                    (dashboard)
```

## ✨ Funcionalidades

- **KPIs generales:** ingreso total, autos lavados, ticket promedio, % de lavados con factura.
- **Tendencia mensual:** ingresos y autos lavados mes a mes.
- **Lavados por día de la semana:** para identificar los días de mayor demanda.
- **Medios de pago:** gráfico de torta + tabla de detalle (monto y cantidad por cada medio).
- **Servicios:** qué tipo de lavado se pide más vs. cuál genera más ingreso.
- **Filtros de mes y de día puntual**, que recalculan todo el resumen al vuelo.
- **Historial por placa:** buscador que muestra todas las visitas anteriores de un vehículo, total gastado y promedio, con paginación.
- **Diseño mobile-first**, pensado para abrirse desde el celular del dueño del negocio.
