# Predict Future Sales – Machine Learning Project

Este proyecto tiene como objetivo predecir la cantidad de productos vendidos por tienda y producto en el próximo mes, utilizando datos históricos de ventas de un e-commerce.

## Descripción del proyecto

Este proyecto aborda un problema real de predicción de demanda en un entorno de comercio electrónico. Utilizando datos históricos de ventas mensuales, tiendas, productos y categorías, el objetivo es construir un modelo que anticipe cuántas unidades se venderán de cada producto en cada tienda durante el próximo mes.

Elegí este proyecto porque conecta directamente con aplicaciones reales en logística, planificación de inventario y optimización de recursos. Además, se basa en un dataset completo y bien documentado disponible en Kaggle, lo que permite aplicar técnicas avanzadas de Machine Learning con impacto en un negocio.

## Objetivo del modelo

El objetivo principal es construir un modelo de Machine Learning que pueda predecir el número de productos vendidos (`item_cnt_month`) por tienda y producto en el mes siguiente (mes 34), basado en los datos históricos de ventas mensuales.

Este modelo busca responder a preguntas clave como:
- ¿Cuántas unidades de un producto se venderán en una tienda específica el próximo mes?
- ¿Qué tiendas tienen mayores volúmenes de venta por categoría?
- ¿Qué productos presentan una tendencia de aumento o disminución en ventas?
- ¿Qué factores históricos (mes, tienda, categoría, producto) influyen en la demanda?

La predicción precisa de la demanda permite optimizar la logística, controlar el inventario y mejorar la toma de decisiones en un negocio de comercio electrónico.

## Fuente de datos

Los datos provienen de la competición de Kaggle [Predict Future Sales](https://www.kaggle.com/competitions/competitive-data-science-predict-future-sales). Este conjunto de datos simula un entorno de ventas mensual en un e-commerce ruso.

Los archivos utilizados en este proyecto son:

- `sales_train.csv`: Histórico de ventas con datos diarios desde enero de 2013 a octubre de 2015.
- `test.csv`: Combinaciones de tienda y producto para las que se debe predecir la venta en noviembre de 2015 (mes 34).
- `items.csv`: Información sobre los productos.
- `item_categories.csv`: Categorías de productos.
- `shops.csv`: Lista de tiendas.

### Resumen de los datos

- `sales_train.csv`: 2.935.849 registros y 6 columnas (`date`, `date_block_num`, `shop_id`, `item_id`, `item_price`, `item_cnt_day`)
- `items.csv`: 22.170 registros con los productos
- `item_categories.csv`: 84 categorías
- `shops.csv`: 60 tiendas

El objetivo es predecir el valor `item_cnt_month` para cada fila del archivo `test.csv`, es decir, cuántas unidades se venderán por tienda y producto en el mes 34.


## Estructura del repositorio

Project_II_ML_Predict_Future_Sales/
│
├── presentation/                 # Presentación final
├── src/
│   ├── data/                     # Archivos originales y procesados (.csv)
│   ├── final_notebook/          # Notebook limpio y final para entrega
│   ├── models/                  # Modelo entrenado (.joblib)
│   ├── notebooks/               # Notebooks por etapa (EDA, limpieza, modelado, etc.)
│   └── utils/                   # Funciones auxiliares (no tenemos)
│
├── README.md                    # Descripción general del proyecto
└── requirements.txt             # Librerías usadas en el entorno


## Resultados del modelo

El modelo final se entrenó usando XGBoostRegressor y se evaluó con la métrica RMSE (Root Mean Squared Error) sobre el conjunto de validación (mes 33).

- Modelo utilizado: XGBoost
- Métrica empleada: RMSE
- Resultado en validación: 0.8958

Este resultado indica que el modelo tiene un buen rendimiento general al predecir ventas mensuales por tienda y producto. Además, se aplicó un recorte (clipping) para que las predicciones se mantuvieran en el rango de 0 a 20, tal como indica la competición de Kaggle.

También se generó el archivo submission.csv con las predicciones finales para el mes 34, listo para subir a la plataforma.


## Autor

Proyecto realizado por Toni Santacruz como parte del Bootcamp de Data Science.

- LinkedIn: https://www.linkedin.com/in/toni-santacruz
- Email: tonisantacruzadam@gmail.com

## Créditos

Este proyecto se basa en los datos proporcionados por la competición de Kaggle:  
Predict Future Sales – https://www.kaggle.com/competitions/competitive-data-science-predict-future-sales

