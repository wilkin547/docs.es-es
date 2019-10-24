---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7aa3755be97a839cb576d53852b75cfe50e39276
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773948"
---
# <a name="client"></a><span data-ttu-id="70258-101">> de \<cliente</span><span class="sxs-lookup"><span data-stu-id="70258-101">\<client></span></span>
<span data-ttu-id="70258-102">El elemento `client` define una lista de extremos a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="70258-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>

<span data-ttu-id="70258-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="70258-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="70258-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="70258-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="70258-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<cliente** ></span><span class="sxs-lookup"><span data-stu-id="70258-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**</span></span>

## <a name="syntax"></a><span data-ttu-id="70258-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70258-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="70258-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="70258-107">Attributes and Elements</span></span>
 <span data-ttu-id="70258-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="70258-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="70258-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="70258-109">Attributes</span></span>
 <span data-ttu-id="70258-110">Ninguno</span><span class="sxs-lookup"><span data-stu-id="70258-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="70258-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="70258-111">Child Elements</span></span>

|<span data-ttu-id="70258-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="70258-112">Element</span></span>|<span data-ttu-id="70258-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="70258-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="70258-114">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="70258-114">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="70258-115">Contiene una colección de elementos de extremo que especifican los puntos de conexión a los que este cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="70258-115">Contains a collection of endpoint elements that specify the endpoints that this client can connect to.</span></span>|
|[<span data-ttu-id="70258-116">metadatos de\<</span><span class="sxs-lookup"><span data-stu-id="70258-116">\<metadata></span></span>](metadata.md)|<span data-ttu-id="70258-117">Contiene los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="70258-117">Contains settings for processing metadata.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="70258-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="70258-118">Parent Elements</span></span>

|<span data-ttu-id="70258-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="70258-119">Element</span></span>|<span data-ttu-id="70258-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="70258-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="70258-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="70258-121">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="70258-122">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="70258-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="70258-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="70258-123">Remarks</span></span>
 <span data-ttu-id="70258-124">La sección `client` define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="70258-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="70258-125">Cada extremo enumerado en la sección de cliente define su propio enlace, comportamiento y contrato.</span><span class="sxs-lookup"><span data-stu-id="70258-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="70258-126">La combinación de los atributos `name` y `contract` identifica singularmente.</span><span class="sxs-lookup"><span data-stu-id="70258-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="70258-127">El código de cliente especifica el `name` para conectar el servicio que el cliente implementa a un extremo.</span><span class="sxs-lookup"><span data-stu-id="70258-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="70258-128">Si se omite el atributo de `name`, el extremo actúa como el extremo predeterminado para el contrato que implementa.</span><span class="sxs-lookup"><span data-stu-id="70258-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>

 <span data-ttu-id="70258-129">Además, esta sección también especifica los valores para procesar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="70258-129">In addition, this section also specifies settings for processing metadata.</span></span>

## <a name="example"></a><span data-ttu-id="70258-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="70258-130">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="70258-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="70258-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="70258-132">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="70258-132">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="70258-133">Clientes</span><span class="sxs-lookup"><span data-stu-id="70258-133">Clients</span></span>](../../../wcf/feature-details/clients.md)
