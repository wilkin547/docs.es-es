---
title: <add> de <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 280c516b17a133930bc4b6621a8c9bc7f4781085
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850565"
---
# <a name="add-of-filters"></a><span data-ttu-id="4ba28-102">\<add> de \<filters></span><span class="sxs-lookup"><span data-stu-id="4ba28-102">\<add> of \<filters></span></span>
<span data-ttu-id="4ba28-103">Filtro de XPath que especifica el tipo de mensaje que se va a registrar.</span><span class="sxs-lookup"><span data-stu-id="4ba28-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<messageLogging>**](messagelogging.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="4ba28-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ba28-104">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ba28-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4ba28-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4ba28-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4ba28-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ba28-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="4ba28-107">Attributes</span></span>  
  
|<span data-ttu-id="4ba28-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="4ba28-108">Attribute</span></span>|<span data-ttu-id="4ba28-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ba28-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ba28-110">filter</span><span class="sxs-lookup"><span data-stu-id="4ba28-110">filter</span></span>|<span data-ttu-id="4ba28-111">Cadena que especifica una consulta en un documento XML definida por una expresión de XPath 1.0.</span><span class="sxs-lookup"><span data-stu-id="4ba28-111">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="4ba28-112">Para obtener más información, vea <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="4ba28-112">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ba28-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4ba28-113">Child Elements</span></span>  
 <span data-ttu-id="4ba28-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4ba28-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ba28-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4ba28-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4ba28-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ba28-116">Element</span></span>|<span data-ttu-id="4ba28-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ba28-117">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters.md)|<span data-ttu-id="4ba28-118">Contiene una colección de filtros de XPath que se utilizan para controlar qué tipo de mensaje se registra.</span><span class="sxs-lookup"><span data-stu-id="4ba28-118">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ba28-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ba28-119">Remarks</span></span>  
 <span data-ttu-id="4ba28-120">Los filtros sólo se aplican en el nivel de transporte, el especificado por `logMessagesAtTransportLevel` es `true`.</span><span class="sxs-lookup"><span data-stu-id="4ba28-120">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="4ba28-121">El nivel de servicio y el registro de mensajes incorrectos no se ven afectados por los filtros.</span><span class="sxs-lookup"><span data-stu-id="4ba28-121">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="4ba28-122">Para agregar un filtro a la colección, utilice la palabra clave `add`.</span><span class="sxs-lookup"><span data-stu-id="4ba28-122">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="4ba28-123">Cuando se definen uno o más filtros, sólo se registran los mensajes que coinciden por lo menos con uno de los filtros.</span><span class="sxs-lookup"><span data-stu-id="4ba28-123">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="4ba28-124">Si no se define ningún filtro, todos los mensajes atraviesan.</span><span class="sxs-lookup"><span data-stu-id="4ba28-124">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="4ba28-125">Los filtros admiten la sintaxis de XPath completa y se aplican en el orden que aparecen en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="4ba28-125">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="4ba28-126">Un filtro con sintaxis incorrecta provoca una excepción de configuración.</span><span class="sxs-lookup"><span data-stu-id="4ba28-126">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="4ba28-127">A continuación, se muestra un ejemplo sobre cómo configurar un filtro que sólo graba mensajes que tienen una sección de encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="4ba28-127">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ba28-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ba28-128">Example</span></span>  
 <span data-ttu-id="4ba28-129">A continuación, se muestra un ejemplo sobre cómo configurar un filtro que sólo graba mensajes que tienen una sección de encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="4ba28-129">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4ba28-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ba28-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="4ba28-131">Configuración del registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="4ba28-131">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [\<messageLogging>](messagelogging.md)
