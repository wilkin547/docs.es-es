---
description: 'Más información acerca de: <diagnostics>'
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: d1651d949cdc095e630e9cde0bacbe51a5eb6062
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782161"
---
# \<diagnostics>

<span data-ttu-id="ac755-102">El elemento `diagnostics` define valores que pueden ser utilizados por un administrador para la inspección y control en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ac755-102">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="ac755-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac755-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac755-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ac755-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ac755-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ac755-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac755-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="ac755-106">Attributes</span></span>  
  
|<span data-ttu-id="ac755-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="ac755-107">Attribute</span></span>|<span data-ttu-id="ac755-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac755-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac755-109">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="ac755-109">etwProviderId</span></span>|<span data-ttu-id="ac755-110">Cadena que especifica el identificador del proveedor de la traza de eventos, que escribe los eventos en las sesiones de ETW.</span><span class="sxs-lookup"><span data-stu-id="ac755-110">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="ac755-111">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="ac755-111">performanceCounters</span></span>|<span data-ttu-id="ac755-112">Especifica si se habilitan los contadores de rendimiento para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ac755-112">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="ac755-113">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="ac755-113">Valid values are</span></span><br /><br /> <span data-ttu-id="ac755-114">-OFF: los contadores de rendimiento están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="ac755-114">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="ac755-115">-ServiceOnly: solo se habilitan los contadores de rendimiento relevantes para este servicio.</span><span class="sxs-lookup"><span data-stu-id="ac755-115">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="ac755-116">-All: los contadores de rendimiento se pueden ver en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ac755-116">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="ac755-117">-Default: se crea una instancia de contador de rendimiento única _WCF_Admin.</span><span class="sxs-lookup"><span data-stu-id="ac755-117">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="ac755-118">Esta instancia se utiliza para habilitar la colección de datos de SQM usados por la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="ac755-118">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="ac755-119">Ninguno de los valores de contador para esta instancia está actualizado y por consiguiente permanecerá a cero.</span><span class="sxs-lookup"><span data-stu-id="ac755-119">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="ac755-120">Éste es el valor predeterminado si ninguna configuración está presente para WCF.</span><span class="sxs-lookup"><span data-stu-id="ac755-120">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="ac755-121">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="ac755-121">wmiProviderEnabled</span></span>|<span data-ttu-id="ac755-122">Un valor booleano que especifica si el proveedor de WMI para el ensamblado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ac755-122">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="ac755-123">El proveedor de WMI se requiere para que el usuario obtenga acceso en tiempo de ejecución a las características de control e inspección de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ac755-123">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="ac755-124">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="ac755-124">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac755-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ac755-125">Child Elements</span></span>  
  
|<span data-ttu-id="ac755-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="ac755-126">Element</span></span>|<span data-ttu-id="ac755-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac755-127">Description</span></span>|  
|-------------|-----------------|  
|[\<endToEndTracing>](endtoendtracing.md)|<span data-ttu-id="ac755-128">Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un extremo a otro durante el funcionamiento de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="ac755-128">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[\<messageLogging>](messagelogging.md)|<span data-ttu-id="ac755-129">Describe los valores para el registro de mensajes WCF.</span><span class="sxs-lookup"><span data-stu-id="ac755-129">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ac755-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ac755-130">Parent Elements</span></span>  
  
|<span data-ttu-id="ac755-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="ac755-131">Element</span></span>|<span data-ttu-id="ac755-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac755-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac755-133">serviceModel</span><span class="sxs-lookup"><span data-stu-id="ac755-133">serviceModel</span></span>|<span data-ttu-id="ac755-134">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="ac755-134">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac755-135">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ac755-135">Remarks</span></span>  

 <span data-ttu-id="ac755-136">La sección `diagnostics` define los valores de diagnóstico para todos los servicios situados en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ac755-136">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="ac755-137">No es posible definir los valores de diagnóstico independientes en el nivel de servicio a menos que sólo haya un servicio en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ac755-137">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="ac755-138">Los atributos se establecen según los requisitos de la sección.</span><span class="sxs-lookup"><span data-stu-id="ac755-138">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac755-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac755-139">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac755-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac755-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
