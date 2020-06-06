---
title: <messageLogging>
ms.date: 03/30/2017
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
ms.openlocfilehash: 9291c38af28c18d20e23e34e8316b4a9fe523123
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855120"
---
# \<messageLogging>
Este elemento define los valores para las funciones del registro de mensajes de Windows Communication Foundation (WCF).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageLogging>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.serviceModel>
  <diagnostics>
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
|`logEntireMessage`|Un valor booleano que especifica si el mensaje completo (encabezado del mensaje y cuerpo) se registra. El valor predeterminado es `false`, que significa que sólo se registra el encabezado del mensaje. Esta configuración afecta a todos los niveles de registro de mensajes (servicio, transporte y mal formado).|  
|`logMalformedMessages`|Un valor booleano que especifica si los mensajes mal formados se registran. Los mensajes incorrectos no cuentan hacia `maxMessagesToLog`. De manera predeterminada, es `false`.|  
|`logMessagesAtServiceLevel`|Un valor booleano que especifica si los mensajes se siguen en el nivel de servicio (antes del cifrado y las transformaciones relacionadas con transporte). De manera predeterminada, es `false`.|  
|`logMessagesAtTransportLevel`|Un valor booleano que especifica si los mensajes se siguen en el nivel de transporte. Se aplica cualquier filtro especificado en el archivo de configuración y sólo se siguen los mensajes que coinciden con los filtros. De manera predeterminada, es `false`.|  
|`maxMessagesToLog`|Un entero positivo que especifica el número máximo de mensajes para registrar. El valor predeterminado es 1000.|  
|`maxSizeOfMessageToLog`|Un entero positivo que especifica el tamaño máximo, en bytes, de un mensaje para registrar. Los mensajes que superen el límite no se registrarán. Este valor afecta a todos los niveles de seguimiento. El valor predeterminado es 262144(0x4000).|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|filters|El elemento `filters` contiene una colección de filtros de XPath. Cuando se habilita el registro de mensajes de transporte (`logMessagesAtTransportLevel` es `true`), sólo los mensajes que coinciden con los filtros se registrarán.<br /><br /> Los filtros sólo se aplican en el nivel de transporte. El nivel de servicio y el registro de mensajes incorrectos no se ven afectados por los filtros.<br /><br /> El único atributo para este elemento, `filter`, es XpathFilter.<br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|diagnóstico|Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.|  
  
## <a name="remarks"></a>Comentarios  
 Los mensajes se registran en tres niveles diferentes: servicio, transporte e incorrectos. Se puede activar cada nivel separadamente.  
  
 Los filtros XPath se pueden agregar  para registrar mensajes concretos en los niveles de servicio y transporte. Si no se define ningún filtro, todos los mensajes se registran. Los filtros sólo se aplican a los encabezados del mensaje. Se omite el cuerpo. WCF omite el cuerpo del mensaje para mejorar el rendimiento. Si desea filtrar en base al contenido del cuerpo, puede crear un agente de escucha personalizado con un filtro que lo haga.  
  
 Necesita crear un agente de seguimiento de escucha para activar la traza del mensaje. El propio agente de escucha puede ser cualquier agente de escucha que funciona con la arquitectura de traza de <xref:System.Diagnostics>. En el siguiente ejemplo se muestra cómo crear el agente de escucha.  
  
```xml  
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel"
            switchValue="Verbose">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="ServiceModel Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
    <source name="System.ServiceModel.MessageLogging">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="MessageLogging Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
  </sources>
  <sharedListeners>
    <add initializeData="C:\ItProTools\TraceLog.xml"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="ServiceModel Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
    <add initializeData="C:\ItProTools\MessageLog.log"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="MessageLogging Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
  </sharedListeners>
</system.diagnostics>
```  
  
## <a name="example"></a>Ejemplo  
  
```xml  
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
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- [Configuración del registro de mensajes](../../../wcf/diagnostics/configuring-message-logging.md)
