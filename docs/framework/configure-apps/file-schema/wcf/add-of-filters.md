---
title: <add> de <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 280c516b17a133930bc4b6621a8c9bc7f4781085
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850565"
---
# <a name="add-of-filters"></a><span data-ttu-id="e5ad3-102">\<Agregar > de \<filtros ></span><span class="sxs-lookup"><span data-stu-id="e5ad3-102">\<add> of \<filters></span></span>
<span data-ttu-id="e5ad3-103">Filtro de XPath que especifica el tipo de mensaje que se va a registrar.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
<span data-ttu-id="e5ad3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5ad3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e5ad3-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e5ad3-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e5ad3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<diagnóstico >** ](diagnostics.md)</span><span class="sxs-lookup"><span data-stu-id="e5ad3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)</span></span>\
<span data-ttu-id="e5ad3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> messageLogging**](messagelogging.md)</span><span class="sxs-lookup"><span data-stu-id="e5ad3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<messageLogging>**](messagelogging.md)</span></span>\
<span data-ttu-id="e5ad3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de filtros**](filters.md)</span><span class="sxs-lookup"><span data-stu-id="e5ad3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters.md)</span></span>\
<span data-ttu-id="e5ad3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="e5ad3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5ad3-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5ad3-110">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5ad3-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e5ad3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e5ad3-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5ad3-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="e5ad3-113">Attributes</span></span>  
  
|<span data-ttu-id="e5ad3-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="e5ad3-114">Attribute</span></span>|<span data-ttu-id="e5ad3-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e5ad3-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5ad3-116">filter</span><span class="sxs-lookup"><span data-stu-id="e5ad3-116">filter</span></span>|<span data-ttu-id="e5ad3-117">Cadena que especifica una consulta en un documento XML definida por una expresión de XPath 1.0.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-117">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="e5ad3-118">Para obtener más información, consulta <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-118">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5ad3-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e5ad3-119">Child Elements</span></span>  
 <span data-ttu-id="e5ad3-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5ad3-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e5ad3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e5ad3-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5ad3-122">Element</span></span>|<span data-ttu-id="e5ad3-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e5ad3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5ad3-124">\<filters></span><span class="sxs-lookup"><span data-stu-id="e5ad3-124">\<filters></span></span>](filters.md)|<span data-ttu-id="e5ad3-125">Contiene una colección de filtros de XPath que se utilizan para controlar qué tipo de mensaje se registra.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-125">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5ad3-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5ad3-126">Remarks</span></span>  
 <span data-ttu-id="e5ad3-127">Los filtros sólo se aplican en el nivel de transporte, el especificado por `logMessagesAtTransportLevel` es `true`.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-127">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="e5ad3-128">El nivel de servicio y el registro de mensajes incorrectos no se ven afectados por los filtros.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-128">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="e5ad3-129">Para agregar un filtro a la colección, utilice la palabra clave `add`.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-129">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="e5ad3-130">Cuando se definen uno o más filtros, sólo se registran los mensajes que coinciden por lo menos con uno de los filtros.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-130">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="e5ad3-131">Si no se define ningún filtro, todos los mensajes atraviesan.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-131">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="e5ad3-132">Los filtros admiten la sintaxis de XPath completa y se aplican en el orden que aparecen en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-132">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="e5ad3-133">Un filtro con sintaxis incorrecta provoca una excepción de configuración.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-133">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="e5ad3-134">A continuación, se muestra un ejemplo sobre cómo configurar un filtro que sólo graba mensajes que tienen una sección de encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-134">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5ad3-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5ad3-135">Example</span></span>  
 <span data-ttu-id="e5ad3-136">A continuación, se muestra un ejemplo sobre cómo configurar un filtro que sólo graba mensajes que tienen una sección de encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="e5ad3-136">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e5ad3-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5ad3-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="e5ad3-138">Configuración del registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="e5ad3-138">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="e5ad3-139">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="e5ad3-139">\<messageLogging></span></span>](messagelogging.md)
