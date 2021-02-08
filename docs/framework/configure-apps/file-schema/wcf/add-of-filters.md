---
description: 'Más información sobre: <add> de <filters>'
title: <add> de <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 546ff41fddfd8a48e14508e27f09236c67c9abc9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802351"
---
# <a name="add-of-filters"></a><span data-ttu-id="91bad-103">\<add> de \<filters></span><span class="sxs-lookup"><span data-stu-id="91bad-103">\<add> of \<filters></span></span>

<span data-ttu-id="91bad-104">Filtro de XPath que especifica el tipo de mensaje que se va a registrar.</span><span class="sxs-lookup"><span data-stu-id="91bad-104">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<messageLogging>**](messagelogging.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="91bad-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91bad-105">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91bad-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="91bad-106">Attributes and Elements</span></span>  

 <span data-ttu-id="91bad-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="91bad-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91bad-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="91bad-108">Attributes</span></span>  
  
|<span data-ttu-id="91bad-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="91bad-109">Attribute</span></span>|<span data-ttu-id="91bad-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="91bad-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="91bad-111">filter</span><span class="sxs-lookup"><span data-stu-id="91bad-111">filter</span></span>|<span data-ttu-id="91bad-112">Cadena que especifica una consulta en un documento XML definida por una expresión de XPath 1.0.</span><span class="sxs-lookup"><span data-stu-id="91bad-112">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="91bad-113">Para obtener más información, vea <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="91bad-113">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91bad-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="91bad-114">Child Elements</span></span>  

 <span data-ttu-id="91bad-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="91bad-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91bad-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="91bad-116">Parent Elements</span></span>  
  
|<span data-ttu-id="91bad-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="91bad-117">Element</span></span>|<span data-ttu-id="91bad-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="91bad-118">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters.md)|<span data-ttu-id="91bad-119">Contiene una colección de filtros de XPath que se utilizan para controlar qué tipo de mensaje se registra.</span><span class="sxs-lookup"><span data-stu-id="91bad-119">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91bad-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="91bad-120">Remarks</span></span>  

 <span data-ttu-id="91bad-121">Los filtros sólo se aplican en el nivel de transporte, el especificado por `logMessagesAtTransportLevel` es `true`.</span><span class="sxs-lookup"><span data-stu-id="91bad-121">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="91bad-122">El nivel de servicio y el registro de mensajes incorrectos no se ven afectados por los filtros.</span><span class="sxs-lookup"><span data-stu-id="91bad-122">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="91bad-123">Para agregar un filtro a la colección, utilice la palabra clave `add`.</span><span class="sxs-lookup"><span data-stu-id="91bad-123">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="91bad-124">Cuando se definen uno o más filtros, sólo se registran los mensajes que coinciden por lo menos con uno de los filtros.</span><span class="sxs-lookup"><span data-stu-id="91bad-124">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="91bad-125">Si no se define ningún filtro, todos los mensajes atraviesan.</span><span class="sxs-lookup"><span data-stu-id="91bad-125">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="91bad-126">Los filtros admiten la sintaxis de XPath completa y se aplican en el orden que aparecen en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="91bad-126">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="91bad-127">Un filtro con sintaxis incorrecta provoca una excepción de configuración.</span><span class="sxs-lookup"><span data-stu-id="91bad-127">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="91bad-128">A continuación, se muestra un ejemplo sobre cómo configurar un filtro que sólo graba mensajes que tienen una sección de encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="91bad-128">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91bad-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91bad-129">Example</span></span>  

 <span data-ttu-id="91bad-130">A continuación, se muestra un ejemplo sobre cómo configurar un filtro que sólo graba mensajes que tienen una sección de encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="91bad-130">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="91bad-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="91bad-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="91bad-132">Configuración del registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="91bad-132">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [\<messageLogging>](messagelogging.md)
