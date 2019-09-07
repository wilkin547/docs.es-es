---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: e6524c18780c062c3b5b7dfc2509449cb208e270
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400433"
---
# <a name="datacontractserializer"></a><span data-ttu-id="ab620-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="ab620-102">dataContractSerializer</span></span>
<span data-ttu-id="ab620-103">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ab620-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
<span data-ttu-id="ab620-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ab620-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ab620-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ab620-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ab620-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ab620-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="ab620-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ab620-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="ab620-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ab620-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="ab620-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> dataContractSerializer**</span><span class="sxs-lookup"><span data-stu-id="ab620-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab620-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab620-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab620-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ab620-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ab620-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ab620-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab620-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="ab620-113">Attributes</span></span>  
  
|<span data-ttu-id="ab620-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ab620-114">Element</span></span>|<span data-ttu-id="ab620-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ab620-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab620-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="ab620-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="ab620-117">Un valor booleano que especifica si se omiten los datos proporcionados por el extremo, cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="ab620-117">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="ab620-118">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="ab620-118">maxItemsInObjectGraph</span></span>|<span data-ttu-id="ab620-119">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="ab620-119">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab620-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ab620-120">Child Elements</span></span>  
 <span data-ttu-id="ab620-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ab620-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab620-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ab620-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ab620-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="ab620-123">Element</span></span>|<span data-ttu-id="ab620-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ab620-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ab620-125">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="ab620-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ab620-126">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ab620-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab620-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab620-127">Remarks</span></span>  
 <span data-ttu-id="ab620-128">Para obtener más información sobre los tipos conocidos, vea la documentación <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ab620-128">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="ab620-129">El elemento de comportamiento `<dataContractSerializer>` (si está presente) debe aparecer siempre antes del elemento de comportamiento `<enableWebScript>` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ab620-129">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="ab620-130">En caso contrario, el comportamiento resultante no está definido.</span><span class="sxs-lookup"><span data-stu-id="ab620-130">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab620-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab620-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="ab620-132">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="ab620-132">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="ab620-133">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="ab620-133">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
