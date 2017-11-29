---
title: '&lt;add&gt; de &lt;serviceActivations&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5166f7859bb3e914de8313de08427cda9bc06d6f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltserviceactivationsgt"></a><span data-ttu-id="d9541-102">&lt;add&gt; de &lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="d9541-102">&lt;add&gt; of &lt;serviceActivations&gt;</span></span>
<span data-ttu-id="d9541-103">Un elemento de configuración que le permite definir la configuración de activación de servicio virtual que se asigna a sus tipos de servicio [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9541-103">A configuration element that allows you to define virtual service activation settings that map to your [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service types.</span></span> <span data-ttu-id="d9541-104">Esto hace posible activar servicios hospedados en WAS/IIS sin un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="d9541-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="d9541-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d9541-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d9541-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="d9541-106">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9541-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9541-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9541-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d9541-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d9541-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d9541-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9541-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d9541-110">Attributes</span></span>  
  
|<span data-ttu-id="d9541-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="d9541-111">Attribute</span></span>|<span data-ttu-id="d9541-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9541-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9541-113">factory</span><span class="sxs-lookup"><span data-stu-id="d9541-113">factory</span></span>|<span data-ttu-id="d9541-114">Cadena que especifica el nombre de tipo de CLR del generador que genera un elemento de activación de servicio.</span><span class="sxs-lookup"><span data-stu-id="d9541-114">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|  
|<span data-ttu-id="d9541-115">servicio</span><span class="sxs-lookup"><span data-stu-id="d9541-115">service</span></span>|<span data-ttu-id="d9541-116">ServiceType que implementa el servicio (Typename calificado completo o Typename corto (cuando se coloca en la carpeta App_Code).</span><span class="sxs-lookup"><span data-stu-id="d9541-116">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|  
|<span data-ttu-id="d9541-117">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="d9541-117">relativeAddress</span></span>|<span data-ttu-id="d9541-118">La dirección relativa dentro de la aplicación de IIS actual (por ejemplo “Service.svc”.</span><span class="sxs-lookup"><span data-stu-id="d9541-118">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="d9541-119">En WCF 4.0 esta dirección relativa debe contener una de las extensiones de archivo conocidas (.svc, .xamlx, …). No tiene que existir ningún archivo físico para relativeUrl</span><span class="sxs-lookup"><span data-stu-id="d9541-119">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9541-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d9541-120">Child Elements</span></span>  
 <span data-ttu-id="d9541-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d9541-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9541-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d9541-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d9541-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9541-123">Element</span></span>|<span data-ttu-id="d9541-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9541-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9541-125">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="d9541-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="d9541-126">Sección de configuración que describe la configuración de activación.</span><span class="sxs-lookup"><span data-stu-id="d9541-126">A configuration section that describes activation settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9541-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9541-127">Remarks</span></span>  
 <span data-ttu-id="d9541-128">En el siguiente ejemplo se muestra cómo configurar los valores de activación dentro del archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="d9541-128">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="d9541-129">Con esta configuración, puede activar GreetingService sin usar un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="d9541-129">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="d9541-130">Observe que `<serviceHostingEnvironment>` es una configuración de nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d9541-130">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="d9541-131">Tiene que colocar el archivo `web.config` que contiene la configuración en la raíz de la aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="d9541-131">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="d9541-132">Además, `serviceHostingEnvironment` es una sección heredable de machinetoApplication.</span><span class="sxs-lookup"><span data-stu-id="d9541-132">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="d9541-133">Si registra un solo servicio en la raíz del equipo, cada servicio de la aplicación heredará este servicio.</span><span class="sxs-lookup"><span data-stu-id="d9541-133">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="d9541-134">La activación basada en la configuración admite la activación a través de protocolos http y distintos de http.</span><span class="sxs-lookup"><span data-stu-id="d9541-134">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="d9541-135">Requiere extensiones en relatativeAddress, es decir .svc, .xoml o .xamlx.</span><span class="sxs-lookup"><span data-stu-id="d9541-135">It requires extensions in the relatativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="d9541-136">Puede asignar sus propias extensiones al buildProviders conocido, que le permitirá activar el servicio a través de cualquier extensión.</span><span class="sxs-lookup"><span data-stu-id="d9541-136">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="d9541-137">Si existe conflicto, la sección `<serviceActivations>` invalida los registros de .svc.</span><span class="sxs-lookup"><span data-stu-id="d9541-137">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9541-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9541-138">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceActivationElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
