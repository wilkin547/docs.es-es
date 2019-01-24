---
title: '&lt;Diagnósticos&gt;'
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: de11145620e8fdf96785908df85ab5ecdfd2e25e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524602"
---
# <a name="ltdiagnosticsgt"></a><span data-ttu-id="451d7-102">&lt;Diagnósticos&gt;</span><span class="sxs-lookup"><span data-stu-id="451d7-102">&lt;diagnostics&gt;</span></span>
<span data-ttu-id="451d7-103">El elemento `diagnostics` define valores que pueden ser utilizados por un administrador para la inspección y control en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="451d7-103">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
 <span data-ttu-id="451d7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="451d7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="451d7-105">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="451d7-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="451d7-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="451d7-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics etwProviderId="String"
               performanceCounters="Off/ServiceOnly/All/Default"
               wmiProviderEnabled="Boolean">
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="451d7-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="451d7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="451d7-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="451d7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="451d7-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="451d7-109">Attributes</span></span>  
  
|<span data-ttu-id="451d7-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="451d7-110">Attribute</span></span>|<span data-ttu-id="451d7-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="451d7-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="451d7-112">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="451d7-112">etwProviderId</span></span>|<span data-ttu-id="451d7-113">Cadena que especifica el identificador del proveedor de la traza de eventos, que escribe los eventos en las sesiones de ETW.</span><span class="sxs-lookup"><span data-stu-id="451d7-113">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="451d7-114">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="451d7-114">performanceCounters</span></span>|<span data-ttu-id="451d7-115">Especifica si se habilitan los contadores de rendimiento para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="451d7-115">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="451d7-116">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="451d7-116">Valid values are</span></span><br /><br /> <span data-ttu-id="451d7-117">-Off: Los contadores de rendimiento están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="451d7-117">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="451d7-118">-   ServiceOnly: Solo los contadores de rendimiento relevantes para este servicio están habilitados.</span><span class="sxs-lookup"><span data-stu-id="451d7-118">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="451d7-119">-Todo: Los contadores de rendimiento se pueden ver en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="451d7-119">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="451d7-120">-Default: Se crea un _WCF_Admin de instancia de contador de rendimiento único.</span><span class="sxs-lookup"><span data-stu-id="451d7-120">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="451d7-121">Esta instancia se utiliza para habilitar la colección de datos de SQM usados por la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="451d7-121">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="451d7-122">Ninguno de los valores de contador para esta instancia está actualizado y por consiguiente permanecerá a cero.</span><span class="sxs-lookup"><span data-stu-id="451d7-122">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="451d7-123">Éste es el valor predeterminado si ninguna configuración está presente para WCF.</span><span class="sxs-lookup"><span data-stu-id="451d7-123">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="451d7-124">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="451d7-124">wmiProviderEnabled</span></span>|<span data-ttu-id="451d7-125">Un valor booleano que especifica si el proveedor de WMI para el ensamblado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="451d7-125">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="451d7-126">El proveedor de WMI se requiere para que el usuario obtenga acceso en tiempo de ejecución a las características de control e inspección de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="451d7-126">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="451d7-127">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="451d7-127">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="451d7-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="451d7-128">Child Elements</span></span>  
  
|<span data-ttu-id="451d7-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="451d7-129">Element</span></span>|<span data-ttu-id="451d7-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="451d7-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="451d7-131">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="451d7-131">\<endToEndTracing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|<span data-ttu-id="451d7-132">Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un punto de conexión a otro durante el funcionamiento de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="451d7-132">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[<span data-ttu-id="451d7-133">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="451d7-133">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|<span data-ttu-id="451d7-134">Describe los valores para el registro de mensajes WCF.</span><span class="sxs-lookup"><span data-stu-id="451d7-134">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="451d7-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="451d7-135">Parent Elements</span></span>  
  
|<span data-ttu-id="451d7-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="451d7-136">Element</span></span>|<span data-ttu-id="451d7-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="451d7-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="451d7-138">serviceModel</span><span class="sxs-lookup"><span data-stu-id="451d7-138">serviceModel</span></span>|<span data-ttu-id="451d7-139">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="451d7-139">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="451d7-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="451d7-140">Remarks</span></span>  
 <span data-ttu-id="451d7-141">La sección `diagnostics` define los valores de diagnóstico para todos los servicios situados en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="451d7-141">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="451d7-142">No es posible definir los valores de diagnóstico independientes en el nivel de servicio a menos que sólo haya un servicio en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="451d7-142">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="451d7-143">Los atributos se establecen según los requisitos de la sección.</span><span class="sxs-lookup"><span data-stu-id="451d7-143">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="451d7-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="451d7-144">Example</span></span>  
  
```xml  
<diagnostics wmiProviderEnabled="false"
             performanceCounters="all">
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
</diagnostics>
```  
  
## <a name="see-also"></a><span data-ttu-id="451d7-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="451d7-145">See also</span></span>
- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
