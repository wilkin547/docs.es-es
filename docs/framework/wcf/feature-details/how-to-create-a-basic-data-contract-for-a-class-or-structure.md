---
title: Procedimiento para crear un contrato de datos básico para una clase o estructura
description: Siga este ejemplo para obtener información sobre cómo crear un contrato de datos mediante una clase o estructura en WCF mediante el atributo DataContractAttribute.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
ms.openlocfilehash: a45fde58795947c3e46fa45750ae1a3faddd8849
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247174"
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="0b422-103">Procedimiento para crear un contrato de datos básico para una clase o estructura</span><span class="sxs-lookup"><span data-stu-id="0b422-103">How to: Create a Basic Data Contract for a Class or Structure</span></span>
<span data-ttu-id="0b422-104">En este tema se muestran los pasos básicos para crear un contrato de datos usando una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="0b422-104">This topic shows the basic steps to create a data contract using a class or structure.</span></span> <span data-ttu-id="0b422-105">Para obtener más información sobre los contratos de datos y cómo se usan, consulte [uso de contratos de datos](using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="0b422-105">For more information about data contracts and how they are used, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="0b422-106">Para ver un tutorial que le guía por los pasos necesarios para crear un servicio y un cliente de Windows Communication Foundation básico (WCF), consulte el [tutorial de introducción](../getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="0b422-106">For a tutorial that walks through the steps of creating a basic Windows Communication Foundation (WCF) service and client, see the [Getting Started Tutorial](../getting-started-tutorial.md).</span></span> <span data-ttu-id="0b422-107">Para obtener una aplicación de ejemplo funcional formada por un servicio y un cliente básicos, vea [contrato de datos básico](../samples/basic-data-contract.md).</span><span class="sxs-lookup"><span data-stu-id="0b422-107">For a working sample application that consists of a basic service and client, see [Basic Data Contract](../samples/basic-data-contract.md).</span></span>  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="0b422-108">Crear un contrato de datos básicos para una clase o estructura</span><span class="sxs-lookup"><span data-stu-id="0b422-108">To create a basic data contract for a class or structure</span></span>  
  
1. <span data-ttu-id="0b422-109">Declare que el tipo tiene un contrato de datos aplicando el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a la clase.</span><span class="sxs-lookup"><span data-stu-id="0b422-109">Declare that the type has a data contract by applying the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class.</span></span> <span data-ttu-id="0b422-110">Observe que todos los tipos públicos, incluidos aquéllos sin atributos, son serializables.</span><span class="sxs-lookup"><span data-stu-id="0b422-110">Note that all public types, including those without attributes, are serializable.</span></span> <span data-ttu-id="0b422-111"><xref:System.Runtime.Serialization.DataContractSerializer> deduce un contrato de datos si el atributo <xref:System.Runtime.Serialization.DataContractAttribute> está ausente.</span><span class="sxs-lookup"><span data-stu-id="0b422-111">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract if the <xref:System.Runtime.Serialization.DataContractAttribute> attribute is absent.</span></span> <span data-ttu-id="0b422-112">Para obtener más información, vea [tipos serializables](serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="0b422-112">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
2. <span data-ttu-id="0b422-113">Defina los miembros (propiedades, campos o eventos) que se serializan aplicando el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a cada miembro.</span><span class="sxs-lookup"><span data-stu-id="0b422-113">Define the members (properties, fields, or events) that are serialized by applying the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each member.</span></span> <span data-ttu-id="0b422-114">Estos miembros se denominan miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="0b422-114">These members are called data members.</span></span> <span data-ttu-id="0b422-115">De forma predeterminada, todos los tipos públicos son serializables.</span><span class="sxs-lookup"><span data-stu-id="0b422-115">By default, all public types are serializable.</span></span> <span data-ttu-id="0b422-116">Para obtener más información, vea [tipos serializables](serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="0b422-116">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0b422-117">Puede aplicar el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a los campos privados y, de este modo, se expondrán los datos a otros.</span><span class="sxs-lookup"><span data-stu-id="0b422-117">You can apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to private fields, causing the data to be exposed to others.</span></span> <span data-ttu-id="0b422-118">Asegúrese de que el miembro no contiene información confidencial.</span><span class="sxs-lookup"><span data-stu-id="0b422-118">Be sure that the member does not contain sensitive data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b422-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b422-119">Example</span></span>  
 <span data-ttu-id="0b422-120">En el ejemplo siguiente, se muestra cómo crear un contrato de datos para el tipo `Person` mediante la aplicación de los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> a la clase y sus miembros.</span><span class="sxs-lookup"><span data-stu-id="0b422-120">The following example shows how to create a data contract for the `Person` type by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the class and its members.</span></span>  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0b422-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b422-121">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="0b422-122">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="0b422-122">Using Data Contracts</span></span>](using-data-contracts.md)
- [<span data-ttu-id="0b422-123">Tutorial de Introducción</span><span class="sxs-lookup"><span data-stu-id="0b422-123">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)
- [<span data-ttu-id="0b422-124">Introducción</span><span class="sxs-lookup"><span data-stu-id="0b422-124">Getting Started</span></span>](../samples/getting-started-sample.md)
