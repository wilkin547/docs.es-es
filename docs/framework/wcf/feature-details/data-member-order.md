---
title: Orden de los miembros de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
ms.openlocfilehash: 717d7014f4c4a56249ead0c839cf05f4f83a6f5f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593469"
---
# <a name="data-member-order"></a><span data-ttu-id="5b7bd-102">Orden de los miembros de datos</span><span class="sxs-lookup"><span data-stu-id="5b7bd-102">Data Member Order</span></span>
<span data-ttu-id="5b7bd-103">En algunas aplicaciones, es útil conocer el orden en el que se envían los datos de los distintos miembros de datos o en el que se espera recibir (como el orden en el que los datos aparecen en el XML serializado).</span><span class="sxs-lookup"><span data-stu-id="5b7bd-103">In some applications, it is useful to know the order in which data from the various data members is sent or is expected to be received (such as the order in which data appears in the serialized XML).</span></span> <span data-ttu-id="5b7bd-104">A veces puede ser necesario cambiar este orden.</span><span class="sxs-lookup"><span data-stu-id="5b7bd-104">Sometimes it may be necessary to change this order.</span></span> <span data-ttu-id="5b7bd-105">En este tema se explican las reglas de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="5b7bd-105">This topic explains the ordering rules.</span></span>  
  
## <a name="basic-rules"></a><span data-ttu-id="5b7bd-106">Reglas básicas</span><span class="sxs-lookup"><span data-stu-id="5b7bd-106">Basic Rules</span></span>  
 <span data-ttu-id="5b7bd-107">Las reglas básicas sobre el orden de los datos incluyen:</span><span class="sxs-lookup"><span data-stu-id="5b7bd-107">The basic rules for data ordering include:</span></span>  
  
- <span data-ttu-id="5b7bd-108">Si un tipo de contrato de datos forma parte de una jerarquía de herencia, los miembros de datos de sus tipos base siempre aparecerán en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="5b7bd-108">If a data contract type is a part of an inheritance hierarchy, data members of its base types are always first in the order.</span></span>  
  
- <span data-ttu-id="5b7bd-109">A continuación, se encontrarán los miembros de datos del tipo actual que no tienen la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> del conjunto de atributos <xref:System.Runtime.Serialization.DataMemberAttribute>, en orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="5b7bd-109">Next in order are the current type’s data members that do not have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set, in alphabetical order.</span></span>  
  
- <span data-ttu-id="5b7bd-110">Después se encontrará cualquier miembro de datos que tenga la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> del conjunto de atributos <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5b7bd-110">Next are any data members that have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set.</span></span> <span data-ttu-id="5b7bd-111">Se ordenan por el valor de la propiedad `Order` y después alfabéticamente si hay más de un miembro de un valor `Order` concreto.</span><span class="sxs-lookup"><span data-stu-id="5b7bd-111">These are ordered by the value of the `Order` property first and then alphabetically if there is more than one member of a certain `Order` value.</span></span> <span data-ttu-id="5b7bd-112">Los valores de orden pueden omitirse.</span><span class="sxs-lookup"><span data-stu-id="5b7bd-112">Order values may be skipped.</span></span>  
  
 <span data-ttu-id="5b7bd-113">El orden alfabético se establece llamando al método <xref:System.String.CompareOrdinal%2A>.</span><span class="sxs-lookup"><span data-stu-id="5b7bd-113">Alphabetical order is established by calling the <xref:System.String.CompareOrdinal%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5b7bd-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5b7bd-114">Examples</span></span>  
 <span data-ttu-id="5b7bd-115">Observe el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="5b7bd-115">Consider the following code.</span></span>  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 <span data-ttu-id="5b7bd-116">El XML generado es similar a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5b7bd-116">The XML produced is similar to the following.</span></span>  
  
```xml  
<DerivedType>  
    <!-- Zebra is a base data member, and appears first. -->  
    <zebra/>
  
    <!-- Cat has no Order, appears alphabetically first. -->  
    <cat/>  
  
   <!-- Dog has no Order, appears alphabetically last. -->  
    <dog/>
  
    <!-- Bird is the member with the smallest Order value -->  
    <bird/>  
  
    <!-- Albatross has the next Order value, alphabetically first. -->  
    <albatross/>  
  
    <!-- Parrot, with the next Order value, alphabetically last. -->  
     <parrot/>  
  
    <!-- Antelope is the member with the highest Order value. Note that   
    Order=2 is skipped -->  
     <antelope/>
</DerivedType>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b7bd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b7bd-117">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- [<span data-ttu-id="5b7bd-118">Equivalencia del contrato de datos</span><span class="sxs-lookup"><span data-stu-id="5b7bd-118">Data Contract Equivalence</span></span>](data-contract-equivalence.md)
- [<span data-ttu-id="5b7bd-119">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="5b7bd-119">Using Data Contracts</span></span>](using-data-contracts.md)
