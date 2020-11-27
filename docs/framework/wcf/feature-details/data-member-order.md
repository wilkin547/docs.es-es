---
title: Orden de los miembros de datos
description: Obtenga información sobre el orden de los miembros de datos en WCF. Es posible que las aplicaciones necesiten conocer o cambiar el orden en el que los miembros de datos se envían o se esperan.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
ms.openlocfilehash: 1cb63569c1789b1577588caf63fb0a0259e530ff
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262169"
---
# <a name="data-member-order"></a><span data-ttu-id="f685f-104">Orden de los miembros de datos</span><span class="sxs-lookup"><span data-stu-id="f685f-104">Data Member Order</span></span>

<span data-ttu-id="f685f-105">En algunas aplicaciones, es útil conocer el orden en el que se envían los datos de los distintos miembros de datos o en el que se espera recibir (como el orden en el que los datos aparecen en el XML serializado).</span><span class="sxs-lookup"><span data-stu-id="f685f-105">In some applications, it is useful to know the order in which data from the various data members is sent or is expected to be received (such as the order in which data appears in the serialized XML).</span></span> <span data-ttu-id="f685f-106">A veces puede ser necesario cambiar este orden.</span><span class="sxs-lookup"><span data-stu-id="f685f-106">Sometimes it may be necessary to change this order.</span></span> <span data-ttu-id="f685f-107">En este tema se explican las reglas de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="f685f-107">This topic explains the ordering rules.</span></span>  
  
## <a name="basic-rules"></a><span data-ttu-id="f685f-108">Reglas básicas</span><span class="sxs-lookup"><span data-stu-id="f685f-108">Basic Rules</span></span>  

 <span data-ttu-id="f685f-109">Las reglas básicas sobre el orden de los datos incluyen:</span><span class="sxs-lookup"><span data-stu-id="f685f-109">The basic rules for data ordering include:</span></span>  
  
- <span data-ttu-id="f685f-110">Si un tipo de contrato de datos forma parte de una jerarquía de herencia, los miembros de datos de sus tipos base siempre aparecerán en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="f685f-110">If a data contract type is a part of an inheritance hierarchy, data members of its base types are always first in the order.</span></span>  
  
- <span data-ttu-id="f685f-111">A continuación, se encontrarán los miembros de datos del tipo actual que no tienen la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> del conjunto de atributos <xref:System.Runtime.Serialization.DataMemberAttribute>, en orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="f685f-111">Next in order are the current type’s data members that do not have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set, in alphabetical order.</span></span>  
  
- <span data-ttu-id="f685f-112">Después se encontrará cualquier miembro de datos que tenga la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> del conjunto de atributos <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f685f-112">Next are any data members that have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set.</span></span> <span data-ttu-id="f685f-113">Se ordenan por el valor de la propiedad `Order` y después alfabéticamente si hay más de un miembro de un valor `Order` concreto.</span><span class="sxs-lookup"><span data-stu-id="f685f-113">These are ordered by the value of the `Order` property first and then alphabetically if there is more than one member of a certain `Order` value.</span></span> <span data-ttu-id="f685f-114">Los valores de orden pueden omitirse.</span><span class="sxs-lookup"><span data-stu-id="f685f-114">Order values may be skipped.</span></span>  
  
 <span data-ttu-id="f685f-115">El orden alfabético se establece llamando al método <xref:System.String.CompareOrdinal%2A>.</span><span class="sxs-lookup"><span data-stu-id="f685f-115">Alphabetical order is established by calling the <xref:System.String.CompareOrdinal%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f685f-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f685f-116">Examples</span></span>  

 <span data-ttu-id="f685f-117">Observe el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f685f-117">Consider the following code.</span></span>  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 <span data-ttu-id="f685f-118">El XML generado es similar a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f685f-118">The XML produced is similar to the following.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f685f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f685f-119">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- [<span data-ttu-id="f685f-120">Equivalencia del contrato de datos</span><span class="sxs-lookup"><span data-stu-id="f685f-120">Data Contract Equivalence</span></span>](data-contract-equivalence.md)
- [<span data-ttu-id="f685f-121">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="f685f-121">Using Data Contracts</span></span>](using-data-contracts.md)
