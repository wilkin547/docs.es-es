---
title: Elemento &lt;add&gt; de &lt;filters&gt;
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 2a26a94c01fdb04b8a9e2d381a28cc909bbdac8f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltfiltersgt"></a>Elemento &lt;add&gt; de &lt;filters&gt;
Filtro de XPath que especifica el tipo de mensaje que se va a registrar.  
  
 \<system.ServiceModel>  
\<diagnóstico >  
\<registro de mensajes >  
\<filtros >  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<filters>  
   <add filter="String"/>  
</filters>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|filtro|Cadena que especifica una consulta en un documento XML definida por una expresión de XPath 1.0. Para obtener más información, consulta <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<filtros >](../../../../../docs/framework/configure-apps/file-schema/wcf/filters.md)|Contiene una colección de filtros de XPath que se utilizan para controlar qué tipo de mensaje se registra.|  
  
## <a name="remarks"></a>Comentarios  
 Los filtros sólo se aplican en el nivel de transporte, el especificado por `logMessagesAtTransportLevel` es `true`. El nivel de servicio y el registro de mensajes incorrectos no se ven afectados por los filtros.  
  
 Para agregar un filtro a la colección, utilice la palabra clave `add`. Cuando se definen uno o más filtros, sólo se registran los mensajes que coinciden por lo menos con uno de los filtros. Si no se define ningún filtro, todos los mensajes atraviesan.  
  
 Los filtros admiten la sintaxis de XPath completa y se aplican en el orden que aparecen en el archivo de configuración. Un filtro con sintaxis incorrecta provoca una excepción de configuración.  
  
 A continuación, se muestra un ejemplo sobre cómo configurar un filtro que sólo graba mensajes que tienen una sección de encabezado SOAP.  
  
## <a name="example"></a>Ejemplo  
 A continuación, se muestra un ejemplo sobre cómo configurar un filtro que sólo graba mensajes que tienen una sección de encabezado SOAP.  
  
```xml  
<messageLogging logEntireMessage="true"  
     logMalformedMessages="true" logMessagesAtServiceLevel="true"  
     logMessagesAtTransportLevel="true" maxMessagesToLog="420">  
     <filters>  
        <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
                        /soap:Envelope/soap:Headers  
        </add>  
     </filters>  
</messageLogging>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>  
 <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>  
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>  
 [Configuración del registro de mensajes](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [Configuración del registro de mensajes](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [\<registro de mensajes >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)
