---
title: "Soporte t&#233;cnico para consultas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Soporte t&#233;cnico para consultas
El almacén de instancias de flujo de trabajo de SQL graba un conjunto de propiedades conocidas en el almacén.Los usuarios pueden consultar instancias basadas en estas propiedades.La siguiente lista contiene algunas de estas propiedades conocidas:  
  
-   **Nombre del sitio.** Nombre del sitio web que contiene el servicio.  
  
-   **Ruta de acceso de aplicación relativa.** Ruta de acceso de la aplicación relativa al sitio web.  
  
-   **Ruta de acceso del servicio relativa.** Ruta de acceso del servicio relativa a la aplicación.  
  
-   **Nombre del servicio.** Nombre del servicio.  
  
-   **Espacio de nombres del servicio.** Nombre del espacio de nombres que usa el servicio.  
  
-   **Equipo actual.**  
  
-   **Último equipo**.El equipo en el que la instancia de servicio del flujo de trabajo se ejecutó la última vez.  
  
> [!NOTE]
>  En el caso de los escenarios auto\-hospedados con el host de servicio de flujo de trabajo, sólo se rellenan las últimas cuatro propiedades.En el caso de escenarios de aplicación de flujo de trabajo, solo se rellena la última propiedad.  
  
 El tiempo de ejecución del flujo de trabajo proporciona los valores para las primeras tres propiedades.El host de servicio de flujo de trabajo proporciona el valor de la propiedad **Motivo de la suspensión**.El propio almacén de instancias de flujo de trabajo de SQL proporciona los valores para la propiedad **Último equipo actualizado**.  
  
 La característica Almacén de instancias de flujo de trabajo SQL también le permite especificar las propiedades personalizadas para las que desea almacenar los valores en la base de datos de persistencia y que desea usar en consultas.Para obtener más información acerca de las promociones personalizadas, vea [Extensibilidad de almacén](../../../docs/framework/windows-workflow-foundation//store-extensibility.md).  
  
## Vistas  
 El almacén de instancias contiene las siguientes vistas.Vea [Esquema de base de datos de persistencia](../../../docs/framework/windows-workflow-foundation//persistence-database-schema.md) para obtener información más detallada.  
  
### Vista Instances  
 La vista Instances contiene los siguientes campos:  
  
1.  **Id**  
  
2.  **PendingTimer**  
  
3.  **CreationTime**  
  
4.  **LastUpdatedTime**  
  
5.  **ServiceDeploymentId**  
  
6.  **SuspensionExceptionName**  
  
7.  **SuspensionReason**  
  
8.  **ActiveBookmarks**  
  
9. **CurrentMachine**  
  
10. **LastMachine**  
  
11. **ExecutionStatus**  
  
12. **IsInitialized**  
  
13. **IsSuspended**  
  
14. **IsCompleted**  
  
15. **EncodingOption**  
  
16. **ReadWritePrimitiveDataProperties**  
  
17. **WriteOnlyPrimitiveDataProperties**  
  
18. **ReadWriteComplexDataProperties**  
  
19. **WriteOnlyComplexDataProperties**  
  
### Vista ServiceDeployments  
 La vista ServiceDeployments contiene los siguientes campos:  
  
1.  **SiteName**  
  
2.  **RelativeServicePath**  
  
3.  **RelativeApplicationPath**  
  
4.  **ServiceName**  
  
5.  **ServiceNamespace**  
  
### Vista InstancePromotedProperties  
 La vista InstancePromotedProperties contiene los siguientes campos.Para obtener detalles sobre las propiedades promovidas, consulte el tema [Extensibilidad de almacén](../../../docs/framework/windows-workflow-foundation//store-extensibility.md).  
  
1.  **InstanceId**  
  
2.  **EncodingOption**  
  
3.  **PromotionName**  
  
4.  **Value\#** \(un intervalo de campos desde **Value1** hasta **Value64**\).