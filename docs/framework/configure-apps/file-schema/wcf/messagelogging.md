---
title: '&lt;registro de mensajes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e5b232e3faf1e0e8976b0c08264c8ba03988902a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagelogginggt"></a><span data-ttu-id="ad5a5-102">&lt;registro de mensajes&gt;</span><span class="sxs-lookup"><span data-stu-id="ad5a5-102">&lt;messageLogging&gt;</span></span>
<span data-ttu-id="ad5a5-103">Este elemento define los valores para las funciones del registro de mensajes de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ad5a5-103">This element defines the settings for the message-logging capabilities of Windows Communication Foundation (WCF).</span></span>  
  
 <span data-ttu-id="ad5a5-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ad5a5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ad5a5-105">\<diagnóstico ></span><span class="sxs-lookup"><span data-stu-id="ad5a5-105">\<diagnostic></span></span>  
<span data-ttu-id="ad5a5-106">\<registro de mensajes ></span><span class="sxs-lookup"><span data-stu-id="ad5a5-106">\<messageLogging></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad5a5-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad5a5-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
       <messageLogging logEntireMessage="Boolean"  
          logMalformedMessages="Boolean"  
          logMessagesAtServiceLevel="Boolean"  
          logMessagesAtTransportLevel="Boolean"  
                    maxMessagesToLog="Integer"  
          maxSizeOfMessageToLog="Integer" >  
          <filters>  
                            <clear />  
          </filters>  
       </messageLogging>  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad5a5-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ad5a5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ad5a5-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad5a5-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="ad5a5-110">Attributes</span></span>  
  
|<span data-ttu-id="ad5a5-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="ad5a5-111">Attribute</span></span>|<span data-ttu-id="ad5a5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad5a5-112">Description</span></span>|  
|---------------|-----------------|  
|`logEntireMessage`|<span data-ttu-id="ad5a5-113">Un valor booleano que especifica si el mensaje completo (encabezado del mensaje y cuerpo) se registra.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-113">A Boolean value that specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="ad5a5-114">El valor predeterminado es `false`, que significa que sólo se registra el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-114">The default is `false`, which means that only the message header is logged.</span></span> <span data-ttu-id="ad5a5-115">Esta configuración afecta a todos los niveles de registro de mensajes (servicio, transporte y mal formado).</span><span class="sxs-lookup"><span data-stu-id="ad5a5-115">This setting affects all message logging levels (service, transport, and malformed).</span></span>|  
|`logMalformedMessages`|<span data-ttu-id="ad5a5-116">Un valor booleano que especifica si los mensajes mal formados se registran.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-116">A Boolean value that specifies whether malformed messages are logged.</span></span> <span data-ttu-id="ad5a5-117">Los mensajes incorrectos no cuentan hacia `maxMessagesToLog`.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-117">Malformed messages do not count toward the `maxMessagesToLog`.</span></span> <span data-ttu-id="ad5a5-118">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-118">The default is `false`.</span></span>|  
|`logMessagesAtServiceLevel`|<span data-ttu-id="ad5a5-119">Un valor booleano que especifica si los mensajes se siguen en el nivel de servicio (antes del cifrado y las transformaciones relacionadas con transporte).</span><span class="sxs-lookup"><span data-stu-id="ad5a5-119">A Boolean value that specifies whether messages are traced at the service level (before encryption- and transport-related transforms).</span></span> <span data-ttu-id="ad5a5-120">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-120">The default is `false`.</span></span>|  
|`logMessagesAtTransportLevel`|<span data-ttu-id="ad5a5-121">Un valor booleano que especifica si los mensajes se siguen en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-121">A Boolean value that specifies whether messages are traced at the transport level.</span></span> <span data-ttu-id="ad5a5-122">Se aplica cualquier filtro especificado en el archivo de configuración y sólo se siguen los mensajes que coinciden con los filtros.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-122">Any filters specified in the config file are applied, and only messages that match the filters are traced.</span></span> <span data-ttu-id="ad5a5-123">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-123">The default is `false`.</span></span>|  
|`maxMessagesToLog`|<span data-ttu-id="ad5a5-124">Un entero positivo que especifica el número máximo de mensajes para registrar.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-124">A positive integer that specifies the maximum number of messages to log.</span></span> <span data-ttu-id="ad5a5-125">El valor predeterminado es 1000.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-125">The default is 1000.</span></span>|  
|`maxSizeOfMessageToLog`|<span data-ttu-id="ad5a5-126">Un entero positivo que especifica el tamaño máximo, en bytes, de un mensaje para registrar.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-126">A positive integer that specifies the maximum size, in bytes, of a message to log.</span></span> <span data-ttu-id="ad5a5-127">Los mensajes que superen el límite no se registrarán.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-127">Messages larger than the limit will not be logged.</span></span> <span data-ttu-id="ad5a5-128">Este valor afecta a todos los niveles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-128">This setting affects all trace levels.</span></span> <span data-ttu-id="ad5a5-129">El valor predeterminado es 262144(0x4000).</span><span class="sxs-lookup"><span data-stu-id="ad5a5-129">The default is 262144(0x4000).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad5a5-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ad5a5-130">Child Elements</span></span>  
  
|<span data-ttu-id="ad5a5-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad5a5-131">Element</span></span>|<span data-ttu-id="ad5a5-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad5a5-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ad5a5-133">filtros</span><span class="sxs-lookup"><span data-stu-id="ad5a5-133">filters</span></span>|<span data-ttu-id="ad5a5-134">El elemento `filters` contiene una colección de filtros de XPath.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-134">The `filters` element holds a collection of XPath filters.</span></span> <span data-ttu-id="ad5a5-135">Cuando se habilita el registro de mensajes de transporte (`logMessagesAtTransportLevel` es `true`), sólo los mensajes que coinciden con los filtros se registrarán.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-135">When transport message logging is enabled (`logMessagesAtTransportLevel` is `true`), only messages matching the filters will be logged.</span></span><br /><br /> <span data-ttu-id="ad5a5-136">Los filtros sólo se aplican en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-136">Filters are applied only at the transport layer.</span></span> <span data-ttu-id="ad5a5-137">El nivel de servicio y el registro de mensajes incorrectos no se ven afectados por los filtros.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-137">Service level and malformed message logging are not affected by filters.</span></span><br /><br /> <span data-ttu-id="ad5a5-138">El único atributo para este elemento, `filter`, es XpathFilter.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-138">The only attribute for this element, `filter`, is an XpathFilter.</span></span><br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad5a5-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ad5a5-139">Parent Elements</span></span>  
  
|<span data-ttu-id="ad5a5-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad5a5-140">Element</span></span>|<span data-ttu-id="ad5a5-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad5a5-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ad5a5-142">diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ad5a5-142">diagnostics</span></span>|<span data-ttu-id="ad5a5-143">Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-143">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad5a5-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad5a5-144">Remarks</span></span>  
 <span data-ttu-id="ad5a5-145">Los mensajes se registran en tres niveles diferentes: servicio, transporte e incorrectos.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-145">Messages are logged at three different levels in the stack: service, transport, and malformed.</span></span> <span data-ttu-id="ad5a5-146">Se puede activar cada nivel separadamente.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-146">Each level can be activated separately.</span></span>  
  
 <span data-ttu-id="ad5a5-147">Los filtros XPath se pueden agregar  para registrar mensajes concretos en los niveles de servicio y transporte.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-147">XPath filters can be added to log specific messages at the transport and service levels.</span></span> <span data-ttu-id="ad5a5-148">Si no se define ningún filtro, todos los mensajes se registran.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-148">If no filters are defined, all messages are logged.</span></span> <span data-ttu-id="ad5a5-149">Los filtros sólo se aplican a los encabezados del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-149">Filters are applied only to the headers of the message.</span></span> <span data-ttu-id="ad5a5-150">Se omite el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-150">The body is ignored.</span></span> <span data-ttu-id="ad5a5-151">WCF omite el cuerpo del mensaje para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-151">WCF ignores the message body to improve performance.</span></span> <span data-ttu-id="ad5a5-152">Si desea filtrar en base al contenido del cuerpo, puede crear un agente de escucha personalizado con un filtro que lo haga.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-152">If you want to filter based on the content of the body, you can create a custom listener with a filter that does so.</span></span>  
  
 <span data-ttu-id="ad5a5-153">Necesita crear un agente de seguimiento de escucha para activar la traza del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-153">You need to create a trace listener to activate message tracing.</span></span> <span data-ttu-id="ad5a5-154">El propio agente de escucha puede ser cualquier agente de escucha que funciona con la arquitectura de traza de <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-154">The listener itself can be any listener that works with the <xref:System.Diagnostics> tracing architecture.</span></span> <span data-ttu-id="ad5a5-155">En el siguiente ejemplo se muestra cómo crear el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="ad5a5-155">The following example demonstrates how to create such a listener.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
          <source name="System.ServiceModel" switchValue="Verbose">  
              <listeners>  
                    <clear />  
                    <add type="System.Diagnostics.DefaultTraceListener" name="Default"  
                        traceOutputOptions="None" />  
                    <add name="ServiceModel Listener" traceOutputOptions="None" />  
               </listeners>  
        </source>  
            <source name="System.ServiceModel.MessageLogging">  
                <listeners>  
                    <clear />  
                    <add type="System.Diagnostics.DefaultTraceListener" name="Default"  
                        traceOutputOptions="None" />  
                    <add name="MessageLogging Listener" traceOutputOptions="None"/>  
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
  
## <a name="example"></a><span data-ttu-id="ad5a5-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad5a5-156">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ad5a5-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad5a5-157">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>  
 [<span data-ttu-id="ad5a5-158">Configurar el registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="ad5a5-158">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)
