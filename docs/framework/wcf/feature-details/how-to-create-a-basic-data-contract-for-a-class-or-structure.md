---
title: "Cómo: Crear un contrato de datos básicos para una clase o estructura"
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
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
caps.latest.revision: "25"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6c5f82e2445e816c4e577e6ce5b0c8c4e2359221
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="44849-102">Cómo: Crear un contrato de datos básicos para una clase o estructura</span><span class="sxs-lookup"><span data-stu-id="44849-102">How to: Create a Basic Data Contract for a Class or Structure</span></span>
<span data-ttu-id="44849-103">En este tema se muestran los pasos básicos para crear un contrato de datos usando una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="44849-103">This topic shows the basic steps to create a data contract using a class or structure.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="44849-104">los contratos de datos y cómo se usan, vea [usar contratos de datos](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="44849-104"> data contracts and how they are used, see [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="44849-105">Para obtener un tutorial que le guía a través de los pasos de creación básico [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] servicio y cliente, consulte la [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="44849-105">For a tutorial that walks through the steps of creating a basic [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and client, see the [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span> <span data-ttu-id="44849-106">Para una aplicación de ejemplo de trabajo que consta de un servicio básico y un cliente, consulte [contrato de datos básica](../../../../docs/framework/wcf/samples/basic-data-contract.md).</span><span class="sxs-lookup"><span data-stu-id="44849-106">For a working sample application that consists of a basic service and client, see [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md).</span></span>  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="44849-107">Crear un contrato de datos básicos para una clase o estructura</span><span class="sxs-lookup"><span data-stu-id="44849-107">To create a basic data contract for a class or structure</span></span>  
  
1.  <span data-ttu-id="44849-108">Declare que el tipo tiene un contrato de datos aplicando el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a la clase.</span><span class="sxs-lookup"><span data-stu-id="44849-108">Declare that the type has a data contract by applying the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class.</span></span> <span data-ttu-id="44849-109">Observe que todos los tipos públicos, incluidos aquéllos sin atributos, son serializables.</span><span class="sxs-lookup"><span data-stu-id="44849-109">Note that all public types, including those without attributes, are serializable.</span></span> <span data-ttu-id="44849-110"><xref:System.Runtime.Serialization.DataContractSerializer> deduce un contrato de datos si el atributo <xref:System.Runtime.Serialization.DataContractAttribute> está ausente.</span><span class="sxs-lookup"><span data-stu-id="44849-110">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract if the <xref:System.Runtime.Serialization.DataContractAttribute> attribute is absent.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="44849-111">[Tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="44849-111"> [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
2.  <span data-ttu-id="44849-112">Defina los miembros (propiedades, campos o eventos) que se serializan aplicando el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a cada miembro.</span><span class="sxs-lookup"><span data-stu-id="44849-112">Define the members (properties, fields, or events) that are serialized by applying the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each member.</span></span> <span data-ttu-id="44849-113">Estos miembros se denominan miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="44849-113">These members are called data members.</span></span> <span data-ttu-id="44849-114">De forma predeterminada, todos los tipos públicos son serializables.</span><span class="sxs-lookup"><span data-stu-id="44849-114">By default, all public types are serializable.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="44849-115">[Tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="44849-115"> [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44849-116">Puede aplicar el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a los campos privados y, de este modo, se expondrán los datos a otros.</span><span class="sxs-lookup"><span data-stu-id="44849-116">You can apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to private fields, causing the data to be exposed to others.</span></span> <span data-ttu-id="44849-117">Asegúrese de que el miembro no contiene información confidencial.</span><span class="sxs-lookup"><span data-stu-id="44849-117">Be sure that the member does not contain sensitive data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44849-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44849-118">Example</span></span>  
 <span data-ttu-id="44849-119">En el ejemplo siguiente, se muestra cómo crear un contrato de datos para el tipo `Person` mediante la aplicación de los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> a la clase y sus miembros.</span><span class="sxs-lookup"><span data-stu-id="44849-119">The following example shows how to create a data contract for the `Person` type by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the class and its members.</span></span>  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="44849-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="44849-120">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [<span data-ttu-id="44849-121">Usar contratos de datos</span><span class="sxs-lookup"><span data-stu-id="44849-121">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="44849-122">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="44849-122">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="44849-123">Introducción</span><span class="sxs-lookup"><span data-stu-id="44849-123">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)
