---
description: 'Más información sobre: <add> de <serviceActivations>'
title: <add> de <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: 53c89321c8cde1966a04870c62fa0777610ff547
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750148"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="1571c-103">\<add> de \<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="1571c-103">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="1571c-104">Un elemento de configuración que le permite definir la configuración de activación de servicio virtual que se asigna a los tipos de servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1571c-104">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="1571c-105">Esto hace posible activar servicios hospedados en WAS/IIS sin un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="1571c-105">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceActivations>**](serviceactivations.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a><span data-ttu-id="1571c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1571c-106">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1571c-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1571c-107">Attributes and Elements</span></span>

<span data-ttu-id="1571c-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1571c-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1571c-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="1571c-109">Attributes</span></span>

|<span data-ttu-id="1571c-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="1571c-110">Attribute</span></span>|<span data-ttu-id="1571c-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="1571c-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="1571c-112">fábrica</span><span class="sxs-lookup"><span data-stu-id="1571c-112">factory</span></span>|<span data-ttu-id="1571c-113">Cadena que especifica el nombre de tipo de CLR del generador que genera un elemento de activación de servicio.</span><span class="sxs-lookup"><span data-stu-id="1571c-113">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="1571c-114">servicio</span><span class="sxs-lookup"><span data-stu-id="1571c-114">service</span></span>|<span data-ttu-id="1571c-115">ServiceType que implementa el servicio (Typename calificado completo o Typename corto (cuando se coloca en la carpeta App_Code).</span><span class="sxs-lookup"><span data-stu-id="1571c-115">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="1571c-116">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="1571c-116">relativeAddress</span></span>|<span data-ttu-id="1571c-117">La dirección relativa dentro de la aplicación de IIS actual (por ejemplo “Service.svc”.</span><span class="sxs-lookup"><span data-stu-id="1571c-117">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="1571c-118">En WCF 4,0, esta dirección relativa debe contener una de las extensiones de archivo conocidas (. SVC,. xamlx,...). No debe existir ningún archivo físico para el relativeUrl</span><span class="sxs-lookup"><span data-stu-id="1571c-118">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="1571c-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1571c-119">Child Elements</span></span>

<span data-ttu-id="1571c-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1571c-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1571c-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1571c-121">Parent Elements</span></span>

|<span data-ttu-id="1571c-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="1571c-122">Element</span></span>|<span data-ttu-id="1571c-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="1571c-123">Description</span></span>|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="1571c-124">Sección de configuración que describe la configuración de activación.</span><span class="sxs-lookup"><span data-stu-id="1571c-124">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1571c-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1571c-125">Remarks</span></span>

<span data-ttu-id="1571c-126">En el siguiente ejemplo se muestra cómo configurar los valores de activación dentro del archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="1571c-126">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="1571c-127">Con esta configuración, puede activar GreetingService sin usar un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="1571c-127">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="1571c-128">Observe que `<serviceHostingEnvironment>` es una configuración de nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1571c-128">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="1571c-129">Tiene que colocar el archivo `web.config` que contiene la configuración en la raíz de la aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="1571c-129">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="1571c-130">Además, `serviceHostingEnvironment` es una sección machineToApplication heredable.</span><span class="sxs-lookup"><span data-stu-id="1571c-130">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="1571c-131">Si registra un solo servicio en la raíz del equipo, cada servicio de la aplicación heredará este servicio.</span><span class="sxs-lookup"><span data-stu-id="1571c-131">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="1571c-132">La activación basada en la configuración admite la activación a través de protocolos http y distintos de http.</span><span class="sxs-lookup"><span data-stu-id="1571c-132">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="1571c-133">Requiere extensiones en relativeAddress, es decir,. SVC,. xoml o. xamlx.</span><span class="sxs-lookup"><span data-stu-id="1571c-133">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="1571c-134">Puede asignar sus propias extensiones al buildProviders conocido, que le permitirá activar el servicio a través de cualquier extensión.</span><span class="sxs-lookup"><span data-stu-id="1571c-134">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="1571c-135">Si existe conflicto, la sección `<serviceActivations>` invalida los registros de .svc.</span><span class="sxs-lookup"><span data-stu-id="1571c-135">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="1571c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="1571c-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
