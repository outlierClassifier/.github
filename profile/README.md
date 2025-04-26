# Sistema de Clasificación Binaria con Arquitectura de Votación

## Descripción General
Sistema de clasificación binaria que implementa un mecanismo de votación entre múltiples modelos de machine learning. La arquitectura cliente-servidor permite procesar datos con estructura temporal y multidimensional provenientes de 8 experimentos (4 de cada clase binaria), utilizando 7 características por experimento y aproximadamente 12,000 mediciones temporales secuenciales por experimento (tomadas cada 16ms).

## Arquitectura
El sistema está dividido en componentes modulares:

### Servidor Central (JavaScript/Node.js)
- Orquesta peticiones a los diversos modelos de clasificación
- Implementa mecanismos de votación (inicialmente por mayoría)
- Proporciona interfaz visual para configuración y visualización
- Maneja timeout y disponibilidad de modelos
- Gestiona asincrónicamente las respuestas de los modelos

### Endpoints de Modelos (Rust/C++)
- APIs independientes implementando tres algoritmos:
  - SVM
  - LSTM
  - XGBoost
- Cada modelo realiza su propio preprocesamiento de datos
- Retorna predicciones y niveles de confianza
- Implementa healthcheck para verificar disponibilidad
