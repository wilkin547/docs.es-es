---
title: Procedimiento Crear un contrato de datos básicos para una clase o estructura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
ms.openlocfilehash: 29105b7f3177403aacf5f8e628f2dceda4e26354
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54747874"
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="1d37e-102">Procedimiento Crear un contrato de datos básicos para una clase o estructura</span><span class="sxs-lookup"><span data-stu-id="1d37e-102">How to: Create a Basic Data Contract for a Class or Structure</span></span>
<span data-ttu-id="1d37e-103">En este tema se muestran los pasos básicos para crear un contrato de datos usando una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="1d37e-103">This topic shows the basic steps to create a data contract using a class or structure.</span></span> <span data-ttu-id="1d37e-104">Para obtener más información acerca de los contratos de datos y cómo se usan, vea [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="1d37e-104">For more information about data contracts and how they are used, see [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="1d37e-105">Para ver un tutorial que le guía a través de los pasos necesarios para crear un servicio de Windows Communication Foundation (WCF) y un cliente básico, consulte el [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="1d37e-105">For a tutorial that walks through the steps of creating a basic Windows Communication Foundation (WCF) service and client, see the [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span> <span data-ttu-id="1d37e-106">Para una aplicación de ejemplo de trabajo que consta de un servicio básico y un cliente, consulte [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md).</span><span class="sxs-lookup"><span data-stu-id="1d37e-106">For a working sample application that consists of a basic service and client, see [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md).</span></span>  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="1d37e-107">Crear un contrato de datos básicos para una clase o estructura</span><span class="sxs-lookup"><span data-stu-id="1d37e-107">To create a basic data contract for a class or structure</span></span>  
  
1.  <span data-ttu-id="1d37e-108">Declare que el tipo tiene un contrato de datos aplicando el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a la clase.</span><span class="sxs-lookup"><span data-stu-id="1d37e-108">Declare that the type has a data contract by applying the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class.</span></span> <span data-ttu-id="1d37e-109">Observe que todos los tipos públicos, incluidos aquéllos sin atributos, son serializables.</span><span class="sxs-lookup"><span data-stu-id="1d37e-109">Note that all public types, including those without attributes, are serializable.</span></span> <span data-ttu-id="1d37e-110"><xref:System.Runtime.Serialization.DataContractSerializer> deduce un contrato de datos si el atributo <xref:System.Runtime.Serialization.DataContractAttribute> está ausente.</span><span class="sxs-lookup"><span data-stu-id="1d37e-110">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract if the <xref:System.Runtime.Serialization.DataContractAttribute> attribute is absent.</span></span> <span data-ttu-id="1d37e-111">Para obtener más información, consulte [tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="1d37e-111">For more information, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
2.  <span data-ttu-id="1d37e-112">Defina los miembros (propiedades, campos o eventos) que se serializan aplicando el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a cada miembro.</span><span class="sxs-lookup"><span data-stu-id="1d37e-112">Define the members (properties, fields, or events) that are serialized by applying the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each member.</span></span> <span data-ttu-id="1d37e-113">Estos miembros se denominan miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="1d37e-113">These members are called data members.</span></span> <span data-ttu-id="1d37e-114">De forma predeterminada, todos los tipos públicos son serializables.</span><span class="sxs-lookup"><span data-stu-id="1d37e-114">By default, all public types are serializable.</span></span> <span data-ttu-id="1d37e-115">Para obtener más información, consulte [tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="1d37e-115">For more information, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1d37e-116">Puede aplicar el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a los campos privados y, de este modo, se expondrán los datos a otros.</span><span class="sxs-lookup"><span data-stu-id="1d37e-116">You can apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to private fields, causing the data to be exposed to others.</span></span> <span data-ttu-id="1d37e-117">Asegúrese de que el miembro no contiene información confidencial.</span><span class="sxs-lookup"><span data-stu-id="1d37e-117">Be sure that the member does not contain sensitive data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d37e-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d37e-118">Example</span></span>  
 <span data-ttu-id="1d37e-119">En el ejemplo siguiente, se muestra cómo crear un contrato de datos para el tipo `Person` mediante la aplicación de los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> a la clase y sus miembros.</span><span class="sxs-lookup"><span data-stu-id="1d37e-119">The following example shows how to create a data contract for the `Person` type by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the class and its members.</span></span>  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1d37e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d37e-120">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="1d37e-121">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="1d37e-121">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="1d37e-122">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="1d37e-122">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)
- [<span data-ttu-id="1d37e-123">Introducción</span><span class="sxs-lookup"><span data-stu-id="1d37e-123">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)
