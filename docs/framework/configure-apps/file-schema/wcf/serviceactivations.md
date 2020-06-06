---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 64ae0bfd90ae941fc78515c7936c998201c87485
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855137"
---
# \<serviceActivations>

<span data-ttu-id="d1891-101">Un elemento de configuración que le permite agregar valores que definen la configuración de activación de servicio virtual que se asignan a los tipos de servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d1891-101">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="d1891-102">Esto hace posible activar servicios hospedados en WAS/IIS sin un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="d1891-102">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceActivations>**  

## <a name="syntax"></a><span data-ttu-id="d1891-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1891-103">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d1891-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d1891-104">Attributes and Elements</span></span>

<span data-ttu-id="d1891-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d1891-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d1891-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="d1891-106">Attributes</span></span>

<span data-ttu-id="d1891-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d1891-107">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d1891-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d1891-108">Child Elements</span></span>

|<span data-ttu-id="d1891-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1891-109">Element</span></span>|<span data-ttu-id="d1891-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1891-110">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-serviceactivations.md)|<span data-ttu-id="d1891-111">Agrega un elemento de configuración que especifica la activación de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="d1891-111">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d1891-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d1891-112">Parent Elements</span></span>

|<span data-ttu-id="d1891-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1891-113">Element</span></span>|<span data-ttu-id="d1891-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1891-114">Description</span></span>|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="d1891-115">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="d1891-115">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d1891-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1891-116">Remarks</span></span>

<span data-ttu-id="d1891-117">En el siguiente ejemplo se muestra cómo configurar los valores de activación dentro del archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="d1891-117">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="d1891-118">Con esta configuración, puede activar GreetingService sin usar un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="d1891-118">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="d1891-119">Observe que `<serviceHostingEnvironment>` es una configuración de nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d1891-119">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="d1891-120">Tiene que colocar el archivo `web.config` que contiene la configuración en la raíz de la aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="d1891-120">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="d1891-121">Además, `serviceHostingEnvironment` es una sección machineToApplication heredable.</span><span class="sxs-lookup"><span data-stu-id="d1891-121">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="d1891-122">Si registra un solo servicio en la raíz del equipo, cada servicio de la aplicación heredará este servicio.</span><span class="sxs-lookup"><span data-stu-id="d1891-122">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="d1891-123">La activación basada en la configuración admite la activación a través de protocolos http y distintos de http.</span><span class="sxs-lookup"><span data-stu-id="d1891-123">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="d1891-124">Requiere extensiones en relativeAddress, es decir,. SVC,. xoml o. xamlx.</span><span class="sxs-lookup"><span data-stu-id="d1891-124">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="d1891-125">Puede asignar sus propias extensiones al buildProviders conocido, que le permitirá activar el servicio a través de cualquier extensión.</span><span class="sxs-lookup"><span data-stu-id="d1891-125">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="d1891-126">Si existe conflicto, la sección `<serviceActivations>` invalida los registros de .svc.</span><span class="sxs-lookup"><span data-stu-id="d1891-126">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1891-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1891-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
