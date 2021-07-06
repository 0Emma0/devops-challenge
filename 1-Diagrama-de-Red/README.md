#### Prueba 1 - Diagrama de Red

Diseñar un diagrama de red en GCP o AWS que cumpla los siguientes requerimientos.

* Soportar cargas variables
* Contar con High Availability
* Frontend en Js
* Consumir dos Microservicios externos
* Una base de datos relacional y una no relacional

**Solución:**

<img src="https://i.ibb.co/5RFfCKg/Diagrama-de-Red.png">

#### Descripción

En el diagrama expuesto, se contempla el uso de Containers para el despliegue del Frontend en Js, ejecutandose sobre la plataforma de Kubernetes para cubrir los aspectos de cargas variables con Horizontal Pod Autoscale, teniendo la posibilidad de escalar los Pods basado en metricas de CPU y Memoria utilizada.

Con respecto a High Availability, se recomienda la implementación de al menos dos nodos de Kubernetes en centros de computos separados en lo se describe en el diseño como Zona A (AZ A) y Zona B (AZ B).

Para el consumo de microservicios externos se utiliza AWS Lambda, servicio que permite ampliar funcionalidades con código personalizado. 

A nivel de bases de datos relacional Amazon RDS provee la posibilidad de implementar instancias de MariaDB, MySQL, Oracle, PostgreSQL y SQL Server. Permitiendo además la configuración Multi-AZ para implementar instancias y replicar datos entre multiples Availabilty Zones.

Finalmente como base de datos no relacional Amazon DynamoDB es un servicio de base de datos NoSQL totalmente administrado que proporciona un rendimiento rápido y predecible con una escalabilidad perfecta.


#### Para el desarrollo de esta prueba se tomo de base la documentación oficial y experiencias adquiridas.

* [Kubernetes - Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/).
* [Kubernetes - HPA](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale-walkthrough/).
* [AWS - Microservicios - Lambda](https://aws.amazon.com/es/lambda/features/).
* [AWS - Amazon RDS MultiAZ](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html).
* [AWS - Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html).




