---
title: <messageLogging>
ms.date: 03/30/2017
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
ms.openlocfilehash: fd4d678b1e861a47762d8a64f85dcc052a30fe2b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204806"
---
# \<messageLogging>

<span data-ttu-id="9066a-101">Este elemento define los valores para las funciones del registro de mensajes de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9066a-101">This element defines the settings for the message-logging capabilities of Windows Communication Foundation (WCF).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageLogging>**  
  
## <a name="syntax"></a><span data-ttu-id="9066a-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9066a-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9066a-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9066a-103">Attributes and Elements</span></span>  

 <span data-ttu-id="9066a-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9066a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9066a-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="9066a-105">Attributes</span></span>  
  
|<span data-ttu-id="9066a-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="9066a-106">Attribute</span></span>|<span data-ttu-id="9066a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9066a-107">Description</span></span>|  
|---------------|-----------------|  
|`logEntireMessage`|<span data-ttu-id="9066a-108">Un valor booleano que especifica si el mensaje completo (encabezado del mensaje y cuerpo) se registra.</span><span class="sxs-lookup"><span data-stu-id="9066a-108">A Boolean value that specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="9066a-109">El valor predeterminado es `false`, que significa que sólo se registra el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9066a-109">The default is `false`, which means that only the message header is logged.</span></span> <span data-ttu-id="9066a-110">Esta configuración afecta a todos los niveles de registro de mensajes (servicio, transporte y mal formado).</span><span class="sxs-lookup"><span data-stu-id="9066a-110">This setting affects all message logging levels (service, transport, and malformed).</span></span>|  
|`logMalformedMessages`|<span data-ttu-id="9066a-111">Un valor booleano que especifica si los mensajes mal formados se registran.</span><span class="sxs-lookup"><span data-stu-id="9066a-111">A Boolean value that specifies whether malformed messages are logged.</span></span> <span data-ttu-id="9066a-112">Los mensajes incorrectos no cuentan hacia `maxMessagesToLog`.</span><span class="sxs-lookup"><span data-stu-id="9066a-112">Malformed messages do not count toward the `maxMessagesToLog`.</span></span> <span data-ttu-id="9066a-113">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="9066a-113">The default is `false`.</span></span>|  
|`logMessagesAtServiceLevel`|<span data-ttu-id="9066a-114">Un valor booleano que especifica si los mensajes se siguen en el nivel de servicio (antes del cifrado y las transformaciones relacionadas con transporte).</span><span class="sxs-lookup"><span data-stu-id="9066a-114">A Boolean value that specifies whether messages are traced at the service level (before encryption- and transport-related transforms).</span></span> <span data-ttu-id="9066a-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="9066a-115">The default is `false`.</span></span>|  
|`logMessagesAtTransportLevel`|<span data-ttu-id="9066a-116">Un valor booleano que especifica si los mensajes se siguen en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="9066a-116">A Boolean value that specifies whether messages are traced at the transport level.</span></span> <span data-ttu-id="9066a-117">Se aplica cualquier filtro especificado en el archivo de configuración y sólo se siguen los mensajes que coinciden con los filtros.</span><span class="sxs-lookup"><span data-stu-id="9066a-117">Any filters specified in the config file are applied, and only messages that match the filters are traced.</span></span> <span data-ttu-id="9066a-118">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="9066a-118">The default is `false`.</span></span>|  
|`maxMessagesToLog`|<span data-ttu-id="9066a-119">Un entero positivo que especifica el número máximo de mensajes para registrar.</span><span class="sxs-lookup"><span data-stu-id="9066a-119">A positive integer that specifies the maximum number of messages to log.</span></span> <span data-ttu-id="9066a-120">El valor predeterminado es 1000.</span><span class="sxs-lookup"><span data-stu-id="9066a-120">The default is 1000.</span></span>|  
|`maxSizeOfMessageToLog`|<span data-ttu-id="9066a-121">Un entero positivo que especifica el tamaño máximo, en bytes, de un mensaje para registrar.</span><span class="sxs-lookup"><span data-stu-id="9066a-121">A positive integer that specifies the maximum size, in bytes, of a message to log.</span></span> <span data-ttu-id="9066a-122">Los mensajes que superen el límite no se registrarán.</span><span class="sxs-lookup"><span data-stu-id="9066a-122">Messages larger than the limit will not be logged.</span></span> <span data-ttu-id="9066a-123">Este valor afecta a todos los niveles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9066a-123">This setting affects all trace levels.</span></span> <span data-ttu-id="9066a-124">El valor predeterminado es 262144(0x4000).</span><span class="sxs-lookup"><span data-stu-id="9066a-124">The default is 262144(0x4000).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9066a-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9066a-125">Child Elements</span></span>  
  
|<span data-ttu-id="9066a-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="9066a-126">Element</span></span>|<span data-ttu-id="9066a-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="9066a-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9066a-128">filters</span><span class="sxs-lookup"><span data-stu-id="9066a-128">filters</span></span>|<span data-ttu-id="9066a-129">El elemento `filters` contiene una colección de filtros de XPath.</span><span class="sxs-lookup"><span data-stu-id="9066a-129">The `filters` element holds a collection of XPath filters.</span></span> <span data-ttu-id="9066a-130">Cuando se habilita el registro de mensajes de transporte (`logMessagesAtTransportLevel` es `true`), sólo los mensajes que coinciden con los filtros se registrarán.</span><span class="sxs-lookup"><span data-stu-id="9066a-130">When transport message logging is enabled (`logMessagesAtTransportLevel` is `true`), only messages matching the filters will be logged.</span></span><br /><br /> <span data-ttu-id="9066a-131">Los filtros sólo se aplican en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="9066a-131">Filters are applied only at the transport layer.</span></span> <span data-ttu-id="9066a-132">El nivel de servicio y el registro de mensajes incorrectos no se ven afectados por los filtros.</span><span class="sxs-lookup"><span data-stu-id="9066a-132">Service level and malformed message logging are not affected by filters.</span></span><br /><br /> <span data-ttu-id="9066a-133">El único atributo para este elemento, `filter`, es XpathFilter.</span><span class="sxs-lookup"><span data-stu-id="9066a-133">The only attribute for this element, `filter`, is an XpathFilter.</span></span><br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a><span data-ttu-id="9066a-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9066a-134">Parent Elements</span></span>  
  
|<span data-ttu-id="9066a-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="9066a-135">Element</span></span>|<span data-ttu-id="9066a-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="9066a-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9066a-137">diagnóstico</span><span class="sxs-lookup"><span data-stu-id="9066a-137">diagnostics</span></span>|<span data-ttu-id="9066a-138">Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.</span><span class="sxs-lookup"><span data-stu-id="9066a-138">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9066a-139">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9066a-139">Remarks</span></span>  

 <span data-ttu-id="9066a-140">Los mensajes se registran en tres niveles diferentes: servicio, transporte e incorrectos.</span><span class="sxs-lookup"><span data-stu-id="9066a-140">Messages are logged at three different levels in the stack: service, transport, and malformed.</span></span> <span data-ttu-id="9066a-141">Se puede activar cada nivel separadamente.</span><span class="sxs-lookup"><span data-stu-id="9066a-141">Each level can be activated separately.</span></span>  
  
 <span data-ttu-id="9066a-142">Los filtros XPath se pueden agregar  para registrar mensajes concretos en los niveles de servicio y transporte.</span><span class="sxs-lookup"><span data-stu-id="9066a-142">XPath filters can be added to log specific messages at the transport and service levels.</span></span> <span data-ttu-id="9066a-143">Si no se define ningún filtro, todos los mensajes se registran.</span><span class="sxs-lookup"><span data-stu-id="9066a-143">If no filters are defined, all messages are logged.</span></span> <span data-ttu-id="9066a-144">Los filtros sólo se aplican a los encabezados del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9066a-144">Filters are applied only to the headers of the message.</span></span> <span data-ttu-id="9066a-145">Se omite el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="9066a-145">The body is ignored.</span></span> <span data-ttu-id="9066a-146">WCF omite el cuerpo del mensaje para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9066a-146">WCF ignores the message body to improve performance.</span></span> <span data-ttu-id="9066a-147">Si desea filtrar en base al contenido del cuerpo, puede crear un agente de escucha personalizado con un filtro que lo haga.</span><span class="sxs-lookup"><span data-stu-id="9066a-147">If you want to filter based on the content of the body, you can create a custom listener with a filter that does so.</span></span>  
  
 <span data-ttu-id="9066a-148">Necesita crear un agente de seguimiento de escucha para activar la traza del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9066a-148">You need to create a trace listener to activate message tracing.</span></span> <span data-ttu-id="9066a-149">El propio agente de escucha puede ser cualquier agente de escucha que funciona con la arquitectura de traza de <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="9066a-149">The listener itself can be any listener that works with the <xref:System.Diagnostics> tracing architecture.</span></span> <span data-ttu-id="9066a-150">En el siguiente ejemplo se muestra cómo crear el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="9066a-150">The following example demonstrates how to create such a listener.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="9066a-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9066a-151">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9066a-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9066a-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- [<span data-ttu-id="9066a-153">Configuración del registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="9066a-153">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
