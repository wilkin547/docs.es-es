---
title: <add> de <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: a0f68717f765482f53e675458fae63d1a374d6fb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850333"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="fcd36-102">\<add> de \<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="fcd36-102">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="fcd36-103">Un elemento de configuración que le permite definir la configuración de activación de servicio virtual que se asigna a los tipos de servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fcd36-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="fcd36-104">Esto hace posible activar servicios hospedados en WAS/IIS sin un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="fcd36-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceActivations>**](serviceactivations.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a><span data-ttu-id="fcd36-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fcd36-105">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fcd36-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fcd36-106">Attributes and Elements</span></span>

<span data-ttu-id="fcd36-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fcd36-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fcd36-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="fcd36-108">Attributes</span></span>

|<span data-ttu-id="fcd36-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="fcd36-109">Attribute</span></span>|<span data-ttu-id="fcd36-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="fcd36-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="fcd36-111">fábrica</span><span class="sxs-lookup"><span data-stu-id="fcd36-111">factory</span></span>|<span data-ttu-id="fcd36-112">Cadena que especifica el nombre de tipo de CLR del generador que genera un elemento de activación de servicio.</span><span class="sxs-lookup"><span data-stu-id="fcd36-112">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="fcd36-113">service</span><span class="sxs-lookup"><span data-stu-id="fcd36-113">service</span></span>|<span data-ttu-id="fcd36-114">ServiceType que implementa el servicio (Typename calificado completo o Typename corto (cuando se coloca en la carpeta App_Code).</span><span class="sxs-lookup"><span data-stu-id="fcd36-114">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="fcd36-115">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="fcd36-115">relativeAddress</span></span>|<span data-ttu-id="fcd36-116">La dirección relativa dentro de la aplicación de IIS actual (por ejemplo “Service.svc”.</span><span class="sxs-lookup"><span data-stu-id="fcd36-116">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="fcd36-117">En WCF 4,0, esta dirección relativa debe contener una de las extensiones de archivo conocidas (. SVC,. xamlx,...). No debe existir ningún archivo físico para el relativeUrl</span><span class="sxs-lookup"><span data-stu-id="fcd36-117">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="fcd36-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fcd36-118">Child Elements</span></span>

<span data-ttu-id="fcd36-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fcd36-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fcd36-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fcd36-120">Parent Elements</span></span>

|<span data-ttu-id="fcd36-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="fcd36-121">Element</span></span>|<span data-ttu-id="fcd36-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="fcd36-122">Description</span></span>|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="fcd36-123">Sección de configuración que describe la configuración de activación.</span><span class="sxs-lookup"><span data-stu-id="fcd36-123">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fcd36-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fcd36-124">Remarks</span></span>

<span data-ttu-id="fcd36-125">En el siguiente ejemplo se muestra cómo configurar los valores de activación dentro del archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="fcd36-125">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="fcd36-126">Con esta configuración, puede activar GreetingService sin usar un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="fcd36-126">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="fcd36-127">Observe que `<serviceHostingEnvironment>` es una configuración de nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="fcd36-127">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="fcd36-128">Tiene que colocar el archivo `web.config` que contiene la configuración en la raíz de la aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="fcd36-128">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="fcd36-129">Además, `serviceHostingEnvironment` es una sección machineToApplication heredable.</span><span class="sxs-lookup"><span data-stu-id="fcd36-129">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="fcd36-130">Si registra un solo servicio en la raíz del equipo, cada servicio de la aplicación heredará este servicio.</span><span class="sxs-lookup"><span data-stu-id="fcd36-130">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="fcd36-131">La activación basada en la configuración admite la activación a través de protocolos http y distintos de http.</span><span class="sxs-lookup"><span data-stu-id="fcd36-131">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="fcd36-132">Requiere extensiones en relativeAddress, es decir,. SVC,. xoml o. xamlx.</span><span class="sxs-lookup"><span data-stu-id="fcd36-132">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="fcd36-133">Puede asignar sus propias extensiones al buildProviders conocido, que le permitirá activar el servicio a través de cualquier extensión.</span><span class="sxs-lookup"><span data-stu-id="fcd36-133">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="fcd36-134">Si existe conflicto, la sección `<serviceActivations>` invalida los registros de .svc.</span><span class="sxs-lookup"><span data-stu-id="fcd36-134">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcd36-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcd36-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
