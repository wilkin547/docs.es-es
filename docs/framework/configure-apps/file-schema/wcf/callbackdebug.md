---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 91e7bd63bf496f2c38776d88173ed2ac12a3b888
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926318"
---
# <a name="callbackdebug"></a>\<callbackDebug>
Especifica la depuración del servicio para un objeto de devolución de llamada de Windows Communication Foundation (WCF).  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<endpointBehaviors>  
\<comportamiento >  
\<callbackDebug>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a>Type  
 `Type`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|Un valor que especifica si los objetos de devolución de llamada de cliente devuelven información de excepción administrada en errores SOAP al servicio.<br /><br /> Si establece este atributo en `true` de manera programática, puede habilitar el flujo de información de excepción administrada en un objeto de devolución de llamada de cliente al servicio de depuración. **Advertencia:**  Devolver información de excepción administrada a los clientes puede ser un riesgo para la seguridad. Esto es porque los detalles de excepción exponen información acerca de la implementación de servicio interna que podría ser usada por clientes no autorizados.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<comportamiento >](behavior-of-endpointbehaviors.md)|Especifica el comportamiento de un punto de conexión.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
