---
description: 'Más información sobre: devoluciones de llamada de serialización Version-Tolerant'
title: Devoluciones de llamadas en la serialización tolerante a versiones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OnDeserializedAttribute [WCF]
- OnDeserializingAttribute [WCF]
- OnSerializingAttribute [WCF]
- serialization [WCF], setting default values
- OnSerializedAttribute [WCF]
ms.assetid: aa4a3a6f-05ec-4efd-bdbf-2181e13e6468
ms.openlocfilehash: 8ee53e96b90ae6b0f2993a543fc129d75eb3481f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756011"
---
# <a name="version-tolerant-serialization-callbacks"></a><span data-ttu-id="01bc3-103">Devoluciones de llamadas en la serialización tolerante a versiones</span><span class="sxs-lookup"><span data-stu-id="01bc3-103">Version-Tolerant Serialization Callbacks</span></span>

<span data-ttu-id="01bc3-104">El modelo de programación del contrato de datos admite totalmente los métodos de devolución de llamada de serialización tolerante a versiones que las clases <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> y <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> admiten.</span><span class="sxs-lookup"><span data-stu-id="01bc3-104">The data contract programming model fully supports the version-tolerant serialization callback methods that the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> and <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> classes support.</span></span>  
  
## <a name="version-tolerant-attributes"></a><span data-ttu-id="01bc3-105">Atributos tolerantes a versiones</span><span class="sxs-lookup"><span data-stu-id="01bc3-105">Version-Tolerant Attributes</span></span>  

 <span data-ttu-id="01bc3-106">Hay cuatro atributos de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="01bc3-106">There are four callback attributes.</span></span> <span data-ttu-id="01bc3-107">Cada atributo se puede aplicar a un método que el motor de serialización/deserialización denomina en varios momentos.</span><span class="sxs-lookup"><span data-stu-id="01bc3-107">Each attribute can be applied to a method that the serialization/deserialization engine calls at various times.</span></span> <span data-ttu-id="01bc3-108">La siguiente tabla explica cuándo utilizar cada atributo.</span><span class="sxs-lookup"><span data-stu-id="01bc3-108">The table below explains when to use each attribute.</span></span>  
  
|<span data-ttu-id="01bc3-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="01bc3-109">Attribute</span></span>|<span data-ttu-id="01bc3-110">Cuando se llama al método correspondiente</span><span class="sxs-lookup"><span data-stu-id="01bc3-110">When the corresponding method is called</span></span>|  
|---------------|---------------------------------------------|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|<span data-ttu-id="01bc3-111">Llamado antes de serializar el tipo.</span><span class="sxs-lookup"><span data-stu-id="01bc3-111">Called before serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|<span data-ttu-id="01bc3-112">Llamado después de serializar el tipo.</span><span class="sxs-lookup"><span data-stu-id="01bc3-112">Called after serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|<span data-ttu-id="01bc3-113">Llamado antes de deserializar el tipo.</span><span class="sxs-lookup"><span data-stu-id="01bc3-113">Called before deserializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|<span data-ttu-id="01bc3-114">Llamado después de deserializar el tipo.</span><span class="sxs-lookup"><span data-stu-id="01bc3-114">Called after deserializing the type.</span></span>|  
  
 <span data-ttu-id="01bc3-115">Los métodos deben aceptar un parámetro <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="01bc3-115">The methods must accept a <xref:System.Runtime.Serialization.StreamingContext> parameter.</span></span>  
  
 <span data-ttu-id="01bc3-116">Estos métodos están pensados principalmente para utilizarlos con controlador de versiones o inicialización.</span><span class="sxs-lookup"><span data-stu-id="01bc3-116">These methods are primarily intended for use with versioning or initialization.</span></span> <span data-ttu-id="01bc3-117">No se llama a ningún constructor durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="01bc3-117">During deserialization, no constructors are called.</span></span> <span data-ttu-id="01bc3-118">Por lo tanto, puede que no se puedan inicializar correctamente los miembros de datos (en valores predeterminados intencionales), si los datos de estos miembros faltan en la secuencia de entrada, por ejemplo, si los datos proceden de una versión anterior de un tipo al cual le faltan algunos miembros de datos. </span><span class="sxs-lookup"><span data-stu-id="01bc3-118">Therefore, data members may not be correctly initialized (to intended default values) if the data for these members is missing in the incoming stream, for example, if the data comes from a previous version of a type that is missing some data members.</span></span> <span data-ttu-id="01bc3-119">Para corregirlo, utilice el método de devolución de llamada marcado con <xref:System.Runtime.Serialization.OnDeserializingAttribute>, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="01bc3-119">To correct this, use the callback method marked with the <xref:System.Runtime.Serialization.OnDeserializingAttribute>, as shown in the following example.</span></span>  
  
 <span data-ttu-id="01bc3-120">Puede marcar sólo un método por tipo con cada uno de los atributos de devolución de llamada anteriores.</span><span class="sxs-lookup"><span data-stu-id="01bc3-120">You can mark only one method per type with each of the preceding callback attributes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="01bc3-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="01bc3-121">Example</span></span>  

 [!code-csharp[C_DataContract#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#9)]
 [!code-vb[C_DataContract#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="01bc3-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="01bc3-122">See also</span></span>

- <xref:System.Runtime.Serialization.OnSerializingAttribute>
- <xref:System.Runtime.Serialization.OnSerializedAttribute>
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>
- <xref:System.Runtime.Serialization.StreamingContext>
- [<span data-ttu-id="01bc3-123">Serialización tolerante a versiones</span><span class="sxs-lookup"><span data-stu-id="01bc3-123">Version Tolerant Serialization</span></span>](../../../standard/serialization/version-tolerant-serialization.md)
