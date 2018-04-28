---
title: 'Cómo: Crear un contrato de datos básicos para una clase o estructura'
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
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f12302fd395197363fe058fe260f717da78145e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a>Cómo: Crear un contrato de datos básicos para una clase o estructura
En este tema se muestran los pasos básicos para crear un contrato de datos usando una clase o estructura. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] los contratos de datos y cómo se usan, vea [usar contratos de datos](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
 Para obtener un tutorial que le guía a través de los pasos de creación básico [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] servicio y cliente, consulte la [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md). Para una aplicación de ejemplo de trabajo que consta de un servicio básico y un cliente, consulte [contrato de datos básica](../../../../docs/framework/wcf/samples/basic-data-contract.md).  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a>Crear un contrato de datos básicos para una clase o estructura  
  
1.  Declare que el tipo tiene un contrato de datos aplicando el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a la clase. Observe que todos los tipos públicos, incluidos aquéllos sin atributos, son serializables. <xref:System.Runtime.Serialization.DataContractSerializer> deduce un contrato de datos si el atributo <xref:System.Runtime.Serialization.DataContractAttribute> está ausente. Para obtener más información, consulte [tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
2.  Defina los miembros (propiedades, campos o eventos) que se serializan aplicando el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a cada miembro. Estos miembros se denominan miembros de datos. De forma predeterminada, todos los tipos públicos son serializables. Para obtener más información, consulte [tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
    > [!NOTE]
    >  Puede aplicar el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a los campos privados y, de este modo, se expondrán los datos a otros. Asegúrese de que el miembro no contiene información confidencial.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se muestra cómo crear un contrato de datos para el tipo `Person` mediante la aplicación de los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> a la clase y sus miembros.  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [Utilización de contratos de datos](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md)
