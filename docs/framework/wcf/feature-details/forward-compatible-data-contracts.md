---
title: Contratos de datos compatibles con el reenvío
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], forward compatibility
ms.assetid: 413c9044-26f8-4ecb-968c-18495ea52cd9
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 554176d2b6ac0c1d5cbe817721c55d06f88457cc
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="forward-compatible-data-contracts"></a><span data-ttu-id="3b97c-102">Contratos de datos compatibles con el reenvío</span><span class="sxs-lookup"><span data-stu-id="3b97c-102">Forward-Compatible Data Contracts</span></span>
<span data-ttu-id="3b97c-103">Una característica del sistema de contrato de datos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] es que los contratos pueden evolucionar con el tiempo sin causar interrupciones.</span><span class="sxs-lookup"><span data-stu-id="3b97c-103">A feature of the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] data contract system is that contracts can evolve over time in nonbreaking ways.</span></span> <span data-ttu-id="3b97c-104">Es decir, un cliente con una versión anterior de un contrato de datos puede comunicarse con un servicio con una versión más reciente del mismo contrato de datos, o un cliente con una versión más reciente de un contrato de datos puede comunicarse con una versión anterior del mismo contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="3b97c-104">That is, a client with an older version of a data contract can communicate with a service with a newer version of the same data contract, or a client with a newer version of a data contract can communicate with an older version of the same data contract.</span></span> <span data-ttu-id="3b97c-105">Para obtener más información, consulte [procedimientos recomendados: control de versiones de contrato de datos](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="3b97c-105">For more information, see [Best Practices: Data Contract Versioning](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md).</span></span>  
  
 <span data-ttu-id="3b97c-106">Puede aplicar la mayoría de las características del control de versiones en la medida que se necesite cuando se crean las nuevas versiones de un contrato del dato existente.</span><span class="sxs-lookup"><span data-stu-id="3b97c-106">You can apply most of the versioning features on an as-needed basis when new versions of an existing data contract are created.</span></span> <span data-ttu-id="3b97c-107">Sin embargo, una característica de control de versiones, *round-tripping*, debe estar integrada en el tipo de la primera versión para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="3b97c-107">However, one versioning feature, *round-tripping*, must be built into the type from the first version in order to work properly.</span></span>  
  
## <a name="round-tripping"></a><span data-ttu-id="3b97c-108">Round-Tripping (recorrido de ida y vuelta)</span><span class="sxs-lookup"><span data-stu-id="3b97c-108">Round-Tripping</span></span>  
 <span data-ttu-id="3b97c-109">Round-tripping tiene lugar cuando los datos pasan de una nueva versión a una versión anterior y de vuelta a la nueva versión de un contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="3b97c-109">Round-tripping occurs when data passes from a new version to an old version and back to the new version of a data contract.</span></span> <span data-ttu-id="3b97c-110">El round-tripping garantiza que no se pierdan datos.</span><span class="sxs-lookup"><span data-stu-id="3b97c-110">Round-tripping guarantees that no data is lost.</span></span> <span data-ttu-id="3b97c-111">Habilitar el round-tripping hace que el tipo sea compatible por adelantado con cualquier cambio futuro admitido por el modelo de control de versiones del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="3b97c-111">Enabling round-tripping makes the type forward-compatible with any future changes supported by the data contract versioning model.</span></span>  
  
 <span data-ttu-id="3b97c-112">Para habilitar el round-tripping para un tipo determinado, el tipo debe implementar la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject>.</span><span class="sxs-lookup"><span data-stu-id="3b97c-112">To enable round-tripping for a particular type, the type must implement the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface.</span></span> <span data-ttu-id="3b97c-113">La interfaz contiene una propiedad, <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> (que devuelve el tipo <xref:System.Runtime.Serialization.ExtensionDataObject> ).</span><span class="sxs-lookup"><span data-stu-id="3b97c-113">The interface contains one property, <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> (returning the <xref:System.Runtime.Serialization.ExtensionDataObject> type).</span></span> <span data-ttu-id="3b97c-114">La propiedad almacena cualquier dato de las versiones futuras del contrato de datos que es desconocido para la versión actual.</span><span class="sxs-lookup"><span data-stu-id="3b97c-114">The property stores any data from future versions of the data contract that is unknown to the current version.</span></span>  
  
### <a name="example"></a><span data-ttu-id="3b97c-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b97c-115">Example</span></span>  
 <span data-ttu-id="3b97c-116">El siguiente contrato de datos no compatible por adelantado con los cambios futuros.</span><span class="sxs-lookup"><span data-stu-id="3b97c-116">The following data contract is not forward-compatible with future changes.</span></span>  
  
 [!code-csharp[C_DataContract#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#7)]
 [!code-vb[C_DataContract#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#7)]  
  
 <span data-ttu-id="3b97c-117">Para hacer que el tipo sea compatible con los cambios futuros (como agregar un nuevo miembro de datos denominado "phoneNumber"), implemente la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject>.</span><span class="sxs-lookup"><span data-stu-id="3b97c-117">To make the type compatible with future changes (such as adding a new data member named "phoneNumber"), implement the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface.</span></span>  
  
 [!code-csharp[C_DataContract#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#8)]
 [!code-vb[C_DataContract#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#8)]  
  
 <span data-ttu-id="3b97c-118">Cuando la infraestructura de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] encuentra datos que no forman parte del contrato de datos original, los datos se almacenan en la propiedad y se conservan.</span><span class="sxs-lookup"><span data-stu-id="3b97c-118">When the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure encounters data that is not part of the original data contract, the data is stored in the property and preserved.</span></span> <span data-ttu-id="3b97c-119">No se procesa para nada más, salvo para el almacenamiento temporal.</span><span class="sxs-lookup"><span data-stu-id="3b97c-119">It is not processed in any other way except for temporary storage.</span></span> <span data-ttu-id="3b97c-120">Si el objeto se devuelve a donde se originó, se devuelven también los datos originales (desconocidos).</span><span class="sxs-lookup"><span data-stu-id="3b97c-120">If the object is returned back to where it originated, the original (unknown) data is also returned.</span></span> <span data-ttu-id="3b97c-121">Por consiguiente, los datos han realizado un viaje de ida y vuelta (round trip) hasta y desde el punto de conexión de origen sin sufrir pérdidas.</span><span class="sxs-lookup"><span data-stu-id="3b97c-121">Therefore, the data has made a round trip to and from the originating endpoint without loss.</span></span> <span data-ttu-id="3b97c-122">Tenga en cuenta, sin embargo, que si el punto de conexión de origen exigiera que se procesasen los datos, la expectativa no se cumple, y el punto de conexión debe detectar y adaptar el cambio de algún modo.</span><span class="sxs-lookup"><span data-stu-id="3b97c-122">Note, however, that if the originating endpoint required the data to be processed, that expectation is unmet, and the endpoint must somehow detect and accommodate the change.</span></span>  
  
 <span data-ttu-id="3b97c-123">El tipo <xref:System.Runtime.Serialization.ExtensionDataObject> no contiene ningún método público ni propiedades.</span><span class="sxs-lookup"><span data-stu-id="3b97c-123">The <xref:System.Runtime.Serialization.ExtensionDataObject> type contains no public methods or properties.</span></span> <span data-ttu-id="3b97c-124">Por tanto, es imposible obtener acceso directo a los datos almacenados dentro de la propiedad <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b97c-124">Thus, it is impossible to get direct access to the data stored inside the <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> property.</span></span>  
  
 <span data-ttu-id="3b97c-125">La característica de round-tripping puede desactivarse, estableciendo `ignoreExtensionDataObject` en `true` en el constructor <xref:System.Runtime.Serialization.DataContractSerializer> o estableciendo la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A> en `true` en el <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3b97c-125">The round-tripping feature may be turned off, either by setting `ignoreExtensionDataObject` to `true` in the <xref:System.Runtime.Serialization.DataContractSerializer> constructor or by setting the <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A> property to `true` on the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="3b97c-126">Cuando esta característica está deshabilitada, el deserializador no rellenará la propiedad <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> y el serializador no emitirá el contenido de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3b97c-126">When this feature is off, the deserializer will not populate the <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> property, and the serializer will not emit the contents of the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b97c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b97c-127">See Also</span></span>  
 <xref:System.Runtime.Serialization.IExtensibleDataObject>  
 <xref:System.Runtime.Serialization.ExtensionDataObject>  
 [<span data-ttu-id="3b97c-128">Versiones de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="3b97c-128">Data Contract Versioning</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)  
 [<span data-ttu-id="3b97c-129">Procedimientos recomendados: creación de versiones de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="3b97c-129">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)
