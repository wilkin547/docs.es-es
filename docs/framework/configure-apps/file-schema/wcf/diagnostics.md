---
description: 'Más información acerca de: <diagnostics>'
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: d1651d949cdc095e630e9cde0bacbe51a5eb6062
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782161"
---
# \<diagnostics>

El elemento `diagnostics` define valores que pueden ser utilizados por un administrador para la inspección y control en tiempo de ejecución.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
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
  
|Atributo|Descripción|  
|---------------|-----------------|  
|etwProviderId|Cadena que especifica el identificador del proveedor de la traza de eventos, que escribe los eventos en las sesiones de ETW.|  
|performanceCounters|Especifica si se habilitan los contadores de rendimiento para el ensamblado. Los valores válidos son<br /><br /> -OFF: los contadores de rendimiento están deshabilitados.<br />-ServiceOnly: solo se habilitan los contadores de rendimiento relevantes para este servicio.<br />-All: los contadores de rendimiento se pueden ver en tiempo de ejecución.<br />-Default: se crea una instancia de contador de rendimiento única _WCF_Admin. Esta instancia se utiliza para habilitar la colección de datos de SQM usados por la infraestructura. Ninguno de los valores de contador para esta instancia está actualizado y por consiguiente permanecerá a cero. Éste es el valor predeterminado si ninguna configuración está presente para WCF.|  
|wmiProviderEnabled|Un valor booleano que especifica si el proveedor de WMI para el ensamblado está habilitado. El proveedor de WMI se requiere para que el usuario obtenga acceso en tiempo de ejecución a las características de control e inspección de Windows Communication Foundation (WCF). De manera predeterminada, es `false`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<endToEndTracing>](endtoendtracing.md)|Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un extremo a otro durante el funcionamiento de una aplicación de servicio.|  
|[\<messageLogging>](messagelogging.md)|Describe los valores para el registro de mensajes WCF.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|serviceModel|Elemento raíz de todos los elementos de configuración de WCF.|  
  
## <a name="remarks"></a>Observaciones  

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
