---
description: 'Más información acerca de: <serviceActivations>'
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 726514af4e42cc387daf61b688d528f690ec8ee8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683026"
---
# \<serviceActivations>

<span data-ttu-id="43034-102">Un elemento de configuración que le permite agregar valores que definen la configuración de activación de servicio virtual que se asignan a los tipos de servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="43034-102">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="43034-103">Esto hace posible activar servicios hospedados en WAS/IIS sin un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="43034-103">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceActivations>**  

## <a name="syntax"></a><span data-ttu-id="43034-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43034-104">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="43034-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="43034-105">Attributes and Elements</span></span>

<span data-ttu-id="43034-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="43034-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="43034-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="43034-107">Attributes</span></span>

<span data-ttu-id="43034-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="43034-108">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="43034-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="43034-109">Child Elements</span></span>

|<span data-ttu-id="43034-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="43034-110">Element</span></span>|<span data-ttu-id="43034-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="43034-111">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-serviceactivations.md)|<span data-ttu-id="43034-112">Agrega un elemento de configuración que especifica la activación de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="43034-112">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="43034-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="43034-113">Parent Elements</span></span>

|<span data-ttu-id="43034-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="43034-114">Element</span></span>|<span data-ttu-id="43034-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="43034-115">Description</span></span>|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="43034-116">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="43034-116">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="43034-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="43034-117">Remarks</span></span>

<span data-ttu-id="43034-118">En el siguiente ejemplo se muestra cómo configurar los valores de activación dentro del archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="43034-118">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="43034-119">Con esta configuración, puede activar GreetingService sin usar un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="43034-119">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="43034-120">Observe que `<serviceHostingEnvironment>` es una configuración de nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="43034-120">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="43034-121">Tiene que colocar el archivo `web.config` que contiene la configuración en la raíz de la aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="43034-121">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="43034-122">Además, `serviceHostingEnvironment` es una sección machineToApplication heredable.</span><span class="sxs-lookup"><span data-stu-id="43034-122">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="43034-123">Si registra un solo servicio en la raíz del equipo, cada servicio de la aplicación heredará este servicio.</span><span class="sxs-lookup"><span data-stu-id="43034-123">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="43034-124">La activación basada en la configuración admite la activación a través de protocolos http y distintos de http.</span><span class="sxs-lookup"><span data-stu-id="43034-124">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="43034-125">Requiere extensiones en relativeAddress, es decir,. SVC,. xoml o. xamlx.</span><span class="sxs-lookup"><span data-stu-id="43034-125">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="43034-126">Puede asignar sus propias extensiones al buildProviders conocido, que le permitirá activar el servicio a través de cualquier extensión.</span><span class="sxs-lookup"><span data-stu-id="43034-126">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="43034-127">Si existe conflicto, la sección `<serviceActivations>` invalida los registros de .svc.</span><span class="sxs-lookup"><span data-stu-id="43034-127">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="43034-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="43034-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
