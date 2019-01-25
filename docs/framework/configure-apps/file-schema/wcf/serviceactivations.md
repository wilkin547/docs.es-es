---
title: '&lt;serviceActivations&gt;'
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 5da05c7b6a9685b9e34b3181ce8e0bd31ccd052b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704961"
---
# <a name="ltserviceactivationsgt"></a><span data-ttu-id="e6870-102">&lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="e6870-102">&lt;serviceActivations&gt;</span></span>
<span data-ttu-id="e6870-103">Un elemento de configuración que le permite agregar valores que definen la configuración de activación de servicio virtual que se asignan a tipos de servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e6870-103">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="e6870-104">Esto hace posible activar servicios hospedados en WAS/IIS sin un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="e6870-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="e6870-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e6870-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e6870-106">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="e6870-106">\<serviceHostingEnvironment></span></span>  
<span data-ttu-id="e6870-107">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="e6870-107">\<serviceActivations></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6870-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6870-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6870-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e6870-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e6870-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e6870-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6870-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e6870-111">Attributes</span></span>  
 <span data-ttu-id="e6870-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e6870-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e6870-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e6870-113">Child Elements</span></span>  
  
|<span data-ttu-id="e6870-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6870-114">Element</span></span>|<span data-ttu-id="e6870-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6870-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6870-116">\<add></span><span class="sxs-lookup"><span data-stu-id="e6870-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|<span data-ttu-id="e6870-117">Agrega un elemento de configuración que especifica la activación de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="e6870-117">Adds a configuration element that specifies the activation of a service application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6870-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e6870-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e6870-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6870-119">Element</span></span>|<span data-ttu-id="e6870-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6870-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6870-121">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="e6870-121">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="e6870-122">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="e6870-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6870-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6870-123">Remarks</span></span>  
 <span data-ttu-id="e6870-124">En el siguiente ejemplo se muestra cómo configurar los valores de activación dentro del archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="e6870-124">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```  
  
 <span data-ttu-id="e6870-125">Con esta configuración, puede activar GreetingService sin usar un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="e6870-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="e6870-126">Observe que `<serviceHostingEnvironment>` es una configuración de nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e6870-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="e6870-127">Tiene que colocar el archivo `web.config` que contiene la configuración en la raíz de la aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="e6870-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="e6870-128">Además, `serviceHostingEnvironment` es una sección heredable de machinetoApplication.</span><span class="sxs-lookup"><span data-stu-id="e6870-128">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="e6870-129">Si registra un solo servicio en la raíz del equipo, cada servicio de la aplicación heredará este servicio.</span><span class="sxs-lookup"><span data-stu-id="e6870-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="e6870-130">La activación basada en la configuración admite la activación a través de protocolos http y distintos de http.</span><span class="sxs-lookup"><span data-stu-id="e6870-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="e6870-131">Requiere extensiones en relatativeAddress, es decir .svc, .xoml o .xamlx.</span><span class="sxs-lookup"><span data-stu-id="e6870-131">It requires extensions in the relatativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="e6870-132">Puede asignar sus propias extensiones al buildProviders conocido, que le permitirá activar el servicio a través de cualquier extensión.</span><span class="sxs-lookup"><span data-stu-id="e6870-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="e6870-133">Si existe conflicto, la sección `<serviceActivations>` invalida los registros de .svc.</span><span class="sxs-lookup"><span data-stu-id="e6870-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6870-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6870-134">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
