---
title: "C&#243;mo: Crear un contrato de datos b&#225;sicos para una clase o estructura | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "contratos de datos [WCF], crear para una clase o estructura"
  - "Clase DataContractAttribute"
  - "DataMemberAttribute"
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# C&#243;mo: Crear un contrato de datos b&#225;sicos para una clase o estructura
En este tema se muestran los pasos básicos para crear un contrato de datos usando una clase o estructura.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] los contratos de datos y cómo se usan, vea [Utilización de contratos de datos](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
 Para obtener un tutorial que explica los pasos para crear un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] básico, consulte [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md).  Para obtener una aplicación de ejemplo operativa compuesta por un servicio básico y cliente, consulte [Contrato de datos básico](../../../../docs/framework/wcf/samples/basic-data-contract.md).  
  
### Crear un contrato de datos básicos para una clase o estructura  
  
1.  Declare que el tipo tiene un contrato de datos aplicando el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a la clase.  Observe que todos los tipos públicos, incluidos aquéllos sin atributos, son serializables.  <xref:System.Runtime.Serialization.DataContractSerializer> deduce un contrato de datos si el atributo <xref:System.Runtime.Serialization.DataContractAttribute> está ausente.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)], vea [Tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
2.  Defina los miembros \(propiedades, campos o eventos\) que se serializan aplicando el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a cada miembro.  Estos miembros se denominan miembros de datos.  De forma predeterminada, todos los tipos públicos son serializables.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)], vea [Tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
    > [!NOTE]
    >  Puede aplicar el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a los campos privados y, de este modo, se expondrán los datos a otros.  Asegúrese de que el miembro no contiene información confidencial.  
  
## Ejemplo  
 En el ejemplo siguiente, se muestra cómo crear un contrato de datos para el tipo `Person` mediante la aplicación de los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> a la clase y sus miembros.  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## Vea también  
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>   
 [Utilización de contratos de datos](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)   
 [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md)   
 [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md)