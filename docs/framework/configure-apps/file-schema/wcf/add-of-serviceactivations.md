---
title: <add> de <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: 2a3ba6d41059a480fe610254c0407df16d149e3b
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57673051"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="13b28-102">\<Agregar > de \<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="13b28-102">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="13b28-103">Un elemento de configuración que le permite definir la configuración de activación de servicio virtual que se asignan a tipos de servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="13b28-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="13b28-104">Esto hace posible activar servicios hospedados en WAS/IIS sin un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="13b28-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="13b28-105">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="13b28-105">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="13b28-106">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="13b28-106">\<serviceHostingEnvironment></span></span>

## <a name="syntax"></a><span data-ttu-id="13b28-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13b28-107">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="13b28-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="13b28-108">Attributes and Elements</span></span>

<span data-ttu-id="13b28-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="13b28-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="13b28-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="13b28-110">Attributes</span></span>

|<span data-ttu-id="13b28-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="13b28-111">Attribute</span></span>|<span data-ttu-id="13b28-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="13b28-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="13b28-113">factory</span><span class="sxs-lookup"><span data-stu-id="13b28-113">factory</span></span>|<span data-ttu-id="13b28-114">Cadena que especifica el nombre de tipo de CLR del generador que genera un elemento de activación de servicio.</span><span class="sxs-lookup"><span data-stu-id="13b28-114">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="13b28-115">servicio</span><span class="sxs-lookup"><span data-stu-id="13b28-115">service</span></span>|<span data-ttu-id="13b28-116">ServiceType que implementa el servicio (Typename calificado completo o Typename corto (cuando se coloca en la carpeta App_Code).</span><span class="sxs-lookup"><span data-stu-id="13b28-116">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="13b28-117">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="13b28-117">relativeAddress</span></span>|<span data-ttu-id="13b28-118">La dirección relativa dentro de la aplicación de IIS actual (por ejemplo “Service.svc”.</span><span class="sxs-lookup"><span data-stu-id="13b28-118">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="13b28-119">En WCF 4.0 esta dirección relativa debe contener una de las extensiones de archivo conocidas (.svc, .xamlx, …). No tiene que existir ningún archivo físico para relativeUrl</span><span class="sxs-lookup"><span data-stu-id="13b28-119">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="13b28-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="13b28-120">Child Elements</span></span>

<span data-ttu-id="13b28-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="13b28-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="13b28-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="13b28-122">Parent Elements</span></span>

|<span data-ttu-id="13b28-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="13b28-123">Element</span></span>|<span data-ttu-id="13b28-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="13b28-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="13b28-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="13b28-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="13b28-126">Sección de configuración que describe la configuración de activación.</span><span class="sxs-lookup"><span data-stu-id="13b28-126">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="13b28-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13b28-127">Remarks</span></span>

<span data-ttu-id="13b28-128">En el siguiente ejemplo se muestra cómo configurar los valores de activación dentro del archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="13b28-128">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="13b28-129">Con esta configuración, puede activar GreetingService sin usar un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="13b28-129">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="13b28-130">Observe que `<serviceHostingEnvironment>` es una configuración de nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="13b28-130">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="13b28-131">Tiene que colocar el archivo `web.config` que contiene la configuración en la raíz de la aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="13b28-131">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="13b28-132">Además, `serviceHostingEnvironment` es una sección heredable de machineToApplication.</span><span class="sxs-lookup"><span data-stu-id="13b28-132">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="13b28-133">Si registra un solo servicio en la raíz del equipo, cada servicio de la aplicación heredará este servicio.</span><span class="sxs-lookup"><span data-stu-id="13b28-133">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="13b28-134">La activación basada en la configuración admite la activación a través de protocolos http y distintos de http.</span><span class="sxs-lookup"><span data-stu-id="13b28-134">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="13b28-135">Requiere extensiones en el relativeAddress, es decir .svc, .xoml o xamlx.</span><span class="sxs-lookup"><span data-stu-id="13b28-135">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="13b28-136">Puede asignar sus propias extensiones al buildProviders conocido, que le permitirá activar el servicio a través de cualquier extensión.</span><span class="sxs-lookup"><span data-stu-id="13b28-136">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="13b28-137">Si existe conflicto, la sección `<serviceActivations>` invalida los registros de .svc.</span><span class="sxs-lookup"><span data-stu-id="13b28-137">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="13b28-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="13b28-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
