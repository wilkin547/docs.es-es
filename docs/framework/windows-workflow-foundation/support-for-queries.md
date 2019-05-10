---
title: Soporte técnico para consultas
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: db3580d0a29353aac027bddd8f040d3085d674af
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665300"
---
# <a name="support-for-queries"></a>Soporte técnico para consultas
El almacén de instancias de flujo de trabajo de SQL graba un conjunto de propiedades conocidas en el almacén. Los usuarios pueden consultar instancias basadas en estas propiedades. La siguiente lista contiene algunas de estas propiedades conocidas:  
  
- **Nombre del sitio.** Nombre del sitio web que contiene el servicio.  
  
- **Ruta de acceso de la aplicación relativa.** Ruta de acceso de la aplicación relativa al sitio web.  
  
- **Ruta de acceso relativa del servicio.** Ruta de acceso del servicio relativa a la aplicación.  
  
- **Nombre de servicio.** Nombre del servicio.  
  
- **Namespace de servicio.** Nombre del espacio de nombres que usa el servicio.  
  
- **Máquina actual.**  
  
- **Último equipo**. El equipo en el que la instancia de servicio del flujo de trabajo se ejecutó la última vez.  
  
> [!NOTE]
>  En el caso de los escenarios auto-hospedados con el host de servicio de flujo de trabajo, sólo se rellenan las últimas cuatro propiedades. En el caso de escenarios de aplicación de flujo de trabajo, solo se rellena la última propiedad.  
  
 El tiempo de ejecución del flujo de trabajo proporciona los valores para las primeras tres propiedades. El host de servicio de flujo de trabajo proporciona el valor de la **motivo de la suspensión** propiedad. El Store de instancia de flujo de trabajo de SQL sí proporciona valores para el **último equipo actualizado** propiedad.  
  
 La característica Almacén de instancias de flujo de trabajo SQL también le permite especificar las propiedades personalizadas para las que desea almacenar los valores en la base de datos de persistencia y que desea usar en consultas. Para obtener más información sobre las promociones personalizadas, vea [Store extensibilidad](store-extensibility.md).  
  
## <a name="views"></a>Vistas  
 El almacén de instancias contiene las siguientes vistas. Consulte [esquema de base de datos de persistencia](persistence-database-schema.md) para obtener más detalles.  
  
### <a name="the-instances-view"></a>Vista Instances  
 La vista Instances contiene los siguientes campos:  
  
1. **Id.**  
  
2. **PendingTimer**  
  
3. **CreationTime**  
  
4. **LastUpdatedTime**  
  
5. **ServiceDeploymentId**  
  
6. **SuspensionExceptionName**  
  
7. **SuspensionReason**  
  
8. **ActiveBookmarks**  
  
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
  
### <a name="the-servicedeployments-view"></a>Vista ServiceDeployments  
 La vista ServiceDeployments contiene los siguientes campos:  
  
1. **SiteName**  
  
2. **RelativeServicePath**  
  
3. **RelativeApplicationPath**  
  
4. **ServiceName**  
  
5. **ServiceNamespace**  
  
### <a name="the-instancepromotedproperties-view"></a>Vista InstancePromotedProperties  
 La vista InstancePromotedProperties contiene los siguientes campos. Para obtener más información sobre las propiedades promovidas, consulte el [Store extensibilidad](store-extensibility.md) tema.  
  
1. **InstanceId**  
  
2. **EncodingOption**  
  
3. **PromotionName**  
  
4. **Value #** (un intervalo de campos de **Value1** a **Value64**).
