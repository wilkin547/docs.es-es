---
title: Elemento &lt;add&gt; de &lt;filters&gt;
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 2a26a94c01fdb04b8a9e2d381a28cc909bbdac8f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754615"
---
# <a name="ltaddgt-of-ltfiltersgt"></a><span data-ttu-id="d6aeb-102">Elemento &lt;add&gt; de &lt;filters&gt;</span><span class="sxs-lookup"><span data-stu-id="d6aeb-102">&lt;add&gt; of &lt;filters&gt;</span></span>
<span data-ttu-id="d6aeb-103">Filtro de XPath que especifica el tipo de mensaje que se va a registrar.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
 <span data-ttu-id="d6aeb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d6aeb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d6aeb-105">\<diagnóstico ></span><span class="sxs-lookup"><span data-stu-id="d6aeb-105">\<diagnostic></span></span>  
<span data-ttu-id="d6aeb-106">\<registro de mensajes ></span><span class="sxs-lookup"><span data-stu-id="d6aeb-106">\<messageLogging></span></span>  
<span data-ttu-id="d6aeb-107">\<filtros ></span><span class="sxs-lookup"><span data-stu-id="d6aeb-107">\<filters></span></span>  
<span data-ttu-id="d6aeb-108">\<add></span><span class="sxs-lookup"><span data-stu-id="d6aeb-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6aeb-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6aeb-109">Syntax</span></span>  
  
```xml  
<filters>  
   <add filter="String"/>  
</filters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6aeb-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d6aeb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d6aeb-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6aeb-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d6aeb-112">Attributes</span></span>  
  
|<span data-ttu-id="d6aeb-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="d6aeb-113">Attribute</span></span>|<span data-ttu-id="d6aeb-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6aeb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d6aeb-115">filtro</span><span class="sxs-lookup"><span data-stu-id="d6aeb-115">filter</span></span>|<span data-ttu-id="d6aeb-116">Cadena que especifica una consulta en un documento XML definida por una expresión de XPath 1.0.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-116">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="d6aeb-117">Para obtener más información, consulta <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-117">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6aeb-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d6aeb-118">Child Elements</span></span>  
 <span data-ttu-id="d6aeb-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6aeb-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d6aeb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d6aeb-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6aeb-121">Element</span></span>|<span data-ttu-id="d6aeb-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6aeb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6aeb-123">\<filtros ></span><span class="sxs-lookup"><span data-stu-id="d6aeb-123">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters.md)|<span data-ttu-id="d6aeb-124">Contiene una colección de filtros de XPath que se utilizan para controlar qué tipo de mensaje se registra.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-124">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6aeb-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6aeb-125">Remarks</span></span>  
 <span data-ttu-id="d6aeb-126">Los filtros sólo se aplican en el nivel de transporte, el especificado por `logMessagesAtTransportLevel` es `true`.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-126">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="d6aeb-127">El nivel de servicio y el registro de mensajes incorrectos no se ven afectados por los filtros.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-127">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="d6aeb-128">Para agregar un filtro a la colección, utilice la palabra clave `add`.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-128">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="d6aeb-129">Cuando se definen uno o más filtros, sólo se registran los mensajes que coinciden por lo menos con uno de los filtros.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-129">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="d6aeb-130">Si no se define ningún filtro, todos los mensajes atraviesan.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-130">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="d6aeb-131">Los filtros admiten la sintaxis de XPath completa y se aplican en el orden que aparecen en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-131">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="d6aeb-132">Un filtro con sintaxis incorrecta provoca una excepción de configuración.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-132">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="d6aeb-133">A continuación, se muestra un ejemplo sobre cómo configurar un filtro que sólo graba mensajes que tienen una sección de encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-133">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6aeb-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6aeb-134">Example</span></span>  
 <span data-ttu-id="d6aeb-135">A continuación, se muestra un ejemplo sobre cómo configurar un filtro que sólo graba mensajes que tienen una sección de encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="d6aeb-135">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d6aeb-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6aeb-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>  
 <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>  
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>  
 [<span data-ttu-id="d6aeb-137">Configuración del registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="d6aeb-137">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [<span data-ttu-id="d6aeb-138">Configuración del registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="d6aeb-138">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [<span data-ttu-id="d6aeb-139">\<registro de mensajes ></span><span class="sxs-lookup"><span data-stu-id="d6aeb-139">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)
