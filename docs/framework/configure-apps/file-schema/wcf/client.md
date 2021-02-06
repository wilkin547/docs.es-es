---
description: 'Más información acerca de: <client>'
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 9765460602738f49963ea521b3f00ed7c63cc568
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638865"
---
# \<client>

<span data-ttu-id="7fde8-102">El elemento `client` define una lista de extremos a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="7fde8-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**

## <a name="syntax"></a><span data-ttu-id="7fde8-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7fde8-103">Syntax</span></span>

```xml
<system.serviceModel>
  <client>
    <endpoint>
    </endpoint>
    <metadata>
    </metadata>
  </client>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7fde8-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7fde8-104">Attributes and Elements</span></span>

 <span data-ttu-id="7fde8-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7fde8-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7fde8-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="7fde8-106">Attributes</span></span>

 <span data-ttu-id="7fde8-107">None</span><span class="sxs-lookup"><span data-stu-id="7fde8-107">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="7fde8-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7fde8-108">Child Elements</span></span>

|<span data-ttu-id="7fde8-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="7fde8-109">Element</span></span>|<span data-ttu-id="7fde8-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7fde8-110">Description</span></span>|
|-------------|-----------------|
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="7fde8-111">Contiene una colección de elementos de extremo que especifican los puntos de conexión a los que este cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="7fde8-111">Contains a collection of endpoint elements that specify the endpoints that this client can connect to.</span></span>|
|[\<metadata>](metadata.md)|<span data-ttu-id="7fde8-112">Contiene los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="7fde8-112">Contains settings for processing metadata.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7fde8-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7fde8-113">Parent Elements</span></span>

|<span data-ttu-id="7fde8-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="7fde8-114">Element</span></span>|<span data-ttu-id="7fde8-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7fde8-115">Description</span></span>|
|-------------|-----------------|
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="7fde8-116">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7fde8-116">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7fde8-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7fde8-117">Remarks</span></span>

 <span data-ttu-id="7fde8-118">La sección `client` define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="7fde8-118">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="7fde8-119">Cada extremo enumerado en la sección de cliente define su propio enlace, comportamiento y contrato.</span><span class="sxs-lookup"><span data-stu-id="7fde8-119">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="7fde8-120">La combinación de los atributos `name` y `contract` identifica singularmente.</span><span class="sxs-lookup"><span data-stu-id="7fde8-120">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="7fde8-121">El código de cliente especifica el `name` para conectar el servicio que el cliente implementa a un extremo.</span><span class="sxs-lookup"><span data-stu-id="7fde8-121">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="7fde8-122">Si se omite el atributo de `name`, el extremo actúa como el extremo predeterminado para el contrato que implementa.</span><span class="sxs-lookup"><span data-stu-id="7fde8-122">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>

 <span data-ttu-id="7fde8-123">Además, esta sección también especifica los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="7fde8-123">In addition, this section also specifies settings for processing metadata.</span></span>

## <a name="example"></a><span data-ttu-id="7fde8-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7fde8-124">Example</span></span>

```xml
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```

## <a name="see-also"></a><span data-ttu-id="7fde8-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fde8-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="7fde8-126">Configuración de cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="7fde8-126">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="7fde8-127">Clientes</span><span class="sxs-lookup"><span data-stu-id="7fde8-127">Clients</span></span>](../../../wcf/feature-details/clients.md)
