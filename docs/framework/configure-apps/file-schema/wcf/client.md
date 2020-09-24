---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: b3234bfa60cd1e3c88778951fc27301c615c84ba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148963"
---
# \<client>

<span data-ttu-id="499b4-101">El elemento `client` define una lista de extremos a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="499b4-101">The `client` element defines a list of endpoints that a client can connect to.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**

## <a name="syntax"></a><span data-ttu-id="499b4-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="499b4-102">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="499b4-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="499b4-103">Attributes and Elements</span></span>

 <span data-ttu-id="499b4-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="499b4-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="499b4-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="499b4-105">Attributes</span></span>

 <span data-ttu-id="499b4-106">None</span><span class="sxs-lookup"><span data-stu-id="499b4-106">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="499b4-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="499b4-107">Child Elements</span></span>

|<span data-ttu-id="499b4-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="499b4-108">Element</span></span>|<span data-ttu-id="499b4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="499b4-109">Description</span></span>|
|-------------|-----------------|
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="499b4-110">Contiene una colección de elementos de extremo que especifican los puntos de conexión a los que este cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="499b4-110">Contains a collection of endpoint elements that specify the endpoints that this client can connect to.</span></span>|
|[\<metadata>](metadata.md)|<span data-ttu-id="499b4-111">Contiene los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="499b4-111">Contains settings for processing metadata.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="499b4-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="499b4-112">Parent Elements</span></span>

|<span data-ttu-id="499b4-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="499b4-113">Element</span></span>|<span data-ttu-id="499b4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="499b4-114">Description</span></span>|
|-------------|-----------------|
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="499b4-115">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="499b4-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="499b4-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="499b4-116">Remarks</span></span>

 <span data-ttu-id="499b4-117">La sección `client` define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="499b4-117">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="499b4-118">Cada extremo enumerado en la sección de cliente define su propio enlace, comportamiento y contrato.</span><span class="sxs-lookup"><span data-stu-id="499b4-118">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="499b4-119">La combinación de los atributos `name` y `contract` identifica singularmente.</span><span class="sxs-lookup"><span data-stu-id="499b4-119">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="499b4-120">El código de cliente especifica el `name` para conectar el servicio que el cliente implementa a un extremo.</span><span class="sxs-lookup"><span data-stu-id="499b4-120">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="499b4-121">Si se omite el atributo de `name`, el extremo actúa como el extremo predeterminado para el contrato que implementa.</span><span class="sxs-lookup"><span data-stu-id="499b4-121">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>

 <span data-ttu-id="499b4-122">Además, esta sección también especifica los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="499b4-122">In addition, this section also specifies settings for processing metadata.</span></span>

## <a name="example"></a><span data-ttu-id="499b4-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="499b4-123">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="499b4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="499b4-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="499b4-125">Configuración de cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="499b4-125">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="499b4-126">Clientes</span><span class="sxs-lookup"><span data-stu-id="499b4-126">Clients</span></span>](../../../wcf/feature-details/clients.md)
