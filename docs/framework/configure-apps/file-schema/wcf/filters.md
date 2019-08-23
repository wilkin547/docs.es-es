---
title: <filters>
ms.date: 03/30/2017
ms.assetid: 37a87222-ec78-4728-8105-9ca1bd961f0c
ms.openlocfilehash: e4ce0452cc46a8f29334fa67f51f14b83290b1c8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918885"
---
# <a name="filters"></a><span data-ttu-id="22432-101">\<filters></span><span class="sxs-lookup"><span data-stu-id="22432-101">\<filters></span></span>

<span data-ttu-id="22432-102">El elemento `filters` contiene una colección de filtros XPath para controlar qué tipo de mensaje está registrado.</span><span class="sxs-lookup"><span data-stu-id="22432-102">The `filters` element holds a collection of XPath filters used to control what kind of message is logged.</span></span>

<span data-ttu-id="22432-103">Los filtros sólo se aplican en el nivel de transporte, el especificado por `logMessagesAtTransportLevel` es `true`.</span><span class="sxs-lookup"><span data-stu-id="22432-103">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="22432-104">El nivel de servicio y el registro de mensajes incorrectos no se ven afectados por los filtros.</span><span class="sxs-lookup"><span data-stu-id="22432-104">Service level and malformed message logging are not affected by filters.</span></span>

<span data-ttu-id="22432-105">Para agregar un filtro a la colección, utilice la palabra clave `add`.</span><span class="sxs-lookup"><span data-stu-id="22432-105">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="22432-106">Cuando se definen uno o más filtros, sólo se registran los mensajes que coinciden por lo menos con uno de los filtros.</span><span class="sxs-lookup"><span data-stu-id="22432-106">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="22432-107">Si no se define ningún filtro, todos los mensajes atraviesan.</span><span class="sxs-lookup"><span data-stu-id="22432-107">If no filter is defined, all messages pass through.</span></span>

<span data-ttu-id="22432-108">Los filtros admiten la sintaxis de XPath completa y se aplican en el orden que aparecen en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="22432-108">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="22432-109">Un filtro con sintaxis incorrecta provoca una excepción de configuración.</span><span class="sxs-lookup"><span data-stu-id="22432-109">A syntactically incorrect filter results in a configuration exception.</span></span>

<span data-ttu-id="22432-110">A continuación, se muestra un ejemplo sobre cómo configurar un filtro que sólo graba mensajes que tienen una sección de encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="22432-110">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="22432-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="22432-111">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="22432-112">Configuración del registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="22432-112">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="22432-113">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="22432-113">\<messageLogging></span></span>](messagelogging.md)
