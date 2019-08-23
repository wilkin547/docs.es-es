---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 170cae5b328c86073c1d8e7710bb19e98ab5688c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925872"
---
# <a name="diagnostics"></a>\<diagnóstico >
El elemento `diagnostics` define valores que pueden ser utilizados por un administrador para la inspección y control en tiempo de ejecución.  
  
 \<system.ServiceModel>  
\<diagnóstico >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.serviceModel>
  <diagnostics etwProviderId="String"
               performanceCounters="Off/ServiceOnly/All/Default"
               wmiProviderEnabled="Boolean">
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|etwProviderId|Cadena que especifica el identificador del proveedor de la traza de eventos, que escribe los eventos en las sesiones de ETW.|  
|performanceCounters|Especifica si se habilitan los contadores de rendimiento para el ensamblado. Los valores válidos son<br /><br /> Habilitar Los contadores de rendimiento están deshabilitados.<br />ServiceOnly Solo los contadores de rendimiento relevantes para este servicio están habilitados.<br />Todos Los contadores de rendimiento se pueden ver en tiempo de ejecución.<br />Predeterminada Se crea un _WCF_Admin de instancia de contador de rendimiento único. Esta instancia se utiliza para habilitar la colección de datos de SQM usados por la infraestructura. Ninguno de los valores de contador para esta instancia está actualizado y por consiguiente permanecerá a cero. Éste es el valor predeterminado si ninguna configuración está presente para WCF.|  
|wmiProviderEnabled|Un valor booleano que especifica si el proveedor de WMI para el ensamblado está habilitado. El proveedor de WMI se requiere para que el usuario obtenga acceso en tiempo de ejecución a las características de control e inspección de Windows Communication Foundation (WCF). El valor predeterminado es `false`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<endToEndTracing>](endtoendtracing.md)|Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un extremo a otro durante el funcionamiento de una aplicación de servicio.|  
|[\<messageLogging>](messagelogging.md)|Describe los valores para el registro de mensajes WCF.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|serviceModel|Elemento raíz de todos los elementos de configuración de WCF.|  
  
## <a name="remarks"></a>Comentarios  
 La sección `diagnostics` define los valores de diagnóstico para todos los servicios situados en un ensamblado. No es posible definir los valores de diagnóstico independientes en el nivel de servicio a menos que sólo haya un servicio en el ensamblado. Los atributos se establecen según los requisitos de la sección.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<diagnostics wmiProviderEnabled="false"
             performanceCounters="all">
  <messageLogging logEntireMessage="true"
                  logMalformedMessages="true"
                  logMessagesAtServiceLevel="true"
                  logMessagesAtTransportLevel="true"
                  maxMessagesToLog="42"
                  maxSizeOfMessageToLog="42">
    <filters>
      <clear />
    </filters>
  </messageLogging>
</diagnostics>
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
