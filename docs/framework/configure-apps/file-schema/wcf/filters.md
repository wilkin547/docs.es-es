---
title: <filters>
ms.date: 03/30/2017
ms.assetid: 37a87222-ec78-4728-8105-9ca1bd961f0c
ms.openlocfilehash: e4ce0452cc46a8f29334fa67f51f14b83290b1c8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "69918885"
---
# \<filters>

El elemento `filters` contiene una colección de filtros XPath para controlar qué tipo de mensaje está registrado.

Los filtros sólo se aplican en el nivel de transporte, el especificado por `logMessagesAtTransportLevel` es `true`. El nivel de servicio y el registro de mensajes incorrectos no se ven afectados por los filtros.

Para agregar un filtro a la colección, utilice la palabra clave `add`. Cuando se definen uno o más filtros, sólo se registran los mensajes que coinciden por lo menos con uno de los filtros. Si no se define ningún filtro, todos los mensajes atraviesan.

Los filtros admiten la sintaxis de XPath completa y se aplican en el orden que aparecen en el archivo de configuración. Un filtro con sintaxis incorrecta provoca una excepción de configuración.

A continuación, se muestra un ejemplo sobre cómo configurar un filtro que sólo graba mensajes que tienen una sección de encabezado SOAP.
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="420">
  <filters>
    <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
      /soap:Envelope/soap:Headers
    </add>
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [Configuración del registro de mensajes](../../../wcf/diagnostics/configuring-message-logging.md)
- [\<messageLogging>](messagelogging.md)
