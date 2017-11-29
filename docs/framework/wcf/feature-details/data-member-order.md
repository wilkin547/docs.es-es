---
title: Orden de los miembros de datos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 06b311f0ca8e9b0a298cd1d9a5e87ff96d13a787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="data-member-order"></a><span data-ttu-id="4755f-102">Orden de los miembros de datos</span><span class="sxs-lookup"><span data-stu-id="4755f-102">Data Member Order</span></span>
<span data-ttu-id="4755f-103">En algunas aplicaciones, es útil conocer el orden en el que se envían los datos de los distintos miembros de datos o en el que se espera recibir (como el orden en el que los datos aparecen en el XML serializado).</span><span class="sxs-lookup"><span data-stu-id="4755f-103">In some applications, it is useful to know the order in which data from the various data members is sent or is expected to be received (such as the order in which data appears in the serialized XML).</span></span> <span data-ttu-id="4755f-104">A veces puede ser necesario cambiar este orden.</span><span class="sxs-lookup"><span data-stu-id="4755f-104">Sometimes it may be necessary to change this order.</span></span> <span data-ttu-id="4755f-105">En este tema se explican las reglas de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="4755f-105">This topic explains the ordering rules.</span></span>  
  
## <a name="basic-rules"></a><span data-ttu-id="4755f-106">Reglas básicas</span><span class="sxs-lookup"><span data-stu-id="4755f-106">Basic Rules</span></span>  
 <span data-ttu-id="4755f-107">Las reglas básicas sobre el orden de los datos incluyen:</span><span class="sxs-lookup"><span data-stu-id="4755f-107">The basic rules for data ordering include:</span></span>  
  
-   <span data-ttu-id="4755f-108">Si un tipo de contrato de datos forma parte de una jerarquía de herencia, los miembros de datos de sus tipos base siempre aparecerán en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="4755f-108">If a data contract type is a part of an inheritance hierarchy, data members of its base types are always first in the order.</span></span>  
  
-   <span data-ttu-id="4755f-109">A continuación, se encontrarán los miembros de datos del tipo actual que no tienen la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> del conjunto de atributos <xref:System.Runtime.Serialization.DataMemberAttribute>, en orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="4755f-109">Next in order are the current type’s data members that do not have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set, in alphabetical order.</span></span>  
  
-   <span data-ttu-id="4755f-110">Después se encontrará cualquier miembro de datos que tenga la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> del conjunto de atributos <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4755f-110">Next are any data members that have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set.</span></span> <span data-ttu-id="4755f-111">Se ordenan por el valor de la propiedad `Order` y después alfabéticamente si hay más de un miembro de un valor `Order` concreto.</span><span class="sxs-lookup"><span data-stu-id="4755f-111">These are ordered by the value of the `Order` property first and then alphabetically if there is more than one member of a certain `Order` value.</span></span> <span data-ttu-id="4755f-112">Los valores de orden pueden omitirse.</span><span class="sxs-lookup"><span data-stu-id="4755f-112">Order values may be skipped.</span></span>  
  
 <span data-ttu-id="4755f-113">El orden alfabético se establece llamando al método <xref:System.String.CompareOrdinal%2A>.</span><span class="sxs-lookup"><span data-stu-id="4755f-113">Alphabetical order is established by calling the <xref:System.String.CompareOrdinal%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4755f-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4755f-114">Examples</span></span>  
 <span data-ttu-id="4755f-115">Observe el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="4755f-115">Consider the following code.</span></span>  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 <span data-ttu-id="4755f-116">El XML generado es similar a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4755f-116">The XML produced is similar to the following.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4755f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4755f-117">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 [<span data-ttu-id="4755f-118">Equivalencia del contrato de datos</span><span class="sxs-lookup"><span data-stu-id="4755f-118">Data Contract Equivalence</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)  
 [<span data-ttu-id="4755f-119">Usar contratos de datos</span><span class="sxs-lookup"><span data-stu-id="4755f-119">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
