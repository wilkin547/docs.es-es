---
title: "Caracter&#237;sticas proporcionadas por System.Transactions  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e458cef9-63b5-4401-b448-1536dcd9d9e5
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Caracter&#237;sticas proporcionadas por System.Transactions 
En esta sección se describe cómo se pueden utilizar las características proporcionadas por el espacio de nombres <xref:System.Transactions> para escribir su propia aplicación transaccional y administrador de recursos.Específicamente, esta sección trata de cómo crear y participar en una transacción \(local o distribuida\) con uno o varios participantes.  
  
## Información general sobre System.Transactions  
 La infraestructura proporcionada por las clases en el espacio de nombres <xref:System.Transactions> hace que la programación transaccional sea sencilla y eficaz en toda la plataforma al admitir las transacciones iniciadas en SQL Server, ADO.NET, Message Queuing \(MSMQ\) y MSDTC \(Coordinador de transacciones distribuidas de Microsoft\).El espacio de nombres <xref:System.Transactions> proporciona un modelo de programación explícito según la clase <xref:System.Transactions.Transaction>, así como un modelo de programación implícito utilizando la clase <xref:System.Transactions.TransactionScope>, en la que la infraestructura administra automáticamente las transacciones.Para obtener más información sobre cómo crear una aplicación transaccional utilizando estos dos modelos, vea [Escribir una aplicación transaccional ](../../../../docs/framework/data/transactions/writing-a-transactional-application.md).  
  
 El espacio de nombres <xref:System.Transactions> también proporciona tipos para implementar un administrador de recursos.Un administrador de recursos administra los datos duraderos o volátiles que se utilizan en una transacción, y trabaja en cooperación con el administrador de transacciones para dotar a la aplicación de una garantía de atomicidad y aislamiento.El administrador de transacciones que proporciona la infraestructura <xref:System.Transactions> admite transacciones que implican varios recursos volátiles o un recurso duradero único.Para más información sobre cómo implementar un administrador de recursos, vea [Implementar un administrador de recursos ](../../../../docs/framework/data/transactions/implementing-a-resource-manager.md).  
  
 Cuando un administrador de recursos duraderos adicional se da de alta a sí mismo en una transacción, el administrador de transacciones también dirige de forma transparente las transacciones locales a transacciones distribuidas, coordinando con un administrador de transacciones basado en disco como DTC.La infraestructura <xref:System.Transactions> proporciona un rendimiento mejorado principalmente de dos formas:  
  
-   Subida dinámica, que asegura que la infraestructura <xref:System.Transactions> solo activa el MSDTC cuando una transacción abarca varios recursos distribuidos.Para obtener más información sobre la elevación dinámica.vea el tema [Extensión de administración de transacciones ](../../../../docs/framework/data/transactions/transaction-management-escalation.md).  
  
-   Inscripciones de ascenso, que permiten que un recurso, como una base de datos, asuma la propiedad de la transacción si es la única entidad que participa en la transacción.Posteriormente, si resulta necesario, la infraestructura <xref:System.Transactions> aún puede dirigir la administración de la transacción a la MSDTC.Esto reduce aún más la oportunidad de utilizar MSDTC.Las inscripciones promocionales se tratan en profundidad en este tema [Optimización mediante el uso de la confirmación de fase única y de la confirmación de fase única promocionable ](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).  
  
 El espacio de nombres <xref:System.Transactions> define tres niveles de confianza \- AllowPartiallyTrustedCallers \(APTCA\), DistributedTransactionPermission \(DTP\) y plena confianza \- que restringe el acceso a los tipos de recursos que expone.Para obtener más información sobre los distintos niveles de confianza, vea [Niveles de confianza de seguridad en el acceso a recursos ](../../../../docs/framework/data/transactions/security-trust-levels-in-accessing-resources.md).  
  
## En esta sección  
  
### Crear una aplicación transaccional  
 El espacio de nombres <xref:System.Transactions> proporciona dos modelos para crear aplicaciones transaccionales.[Implementar una transacción implícita utilizando el ámbito de transacción ](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) describe cómo el espacio de nombres <xref:System.Transactions> admite la creación de transacciones implícitas usando la clase <xref:System.Transactions.TransactionScope>.  
  
 [Implementar una transacción explícita utilizando CommittableTransaction ](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md) describe cómo el espacio de nombres <xref:System.Transactions> admite la creación de transacciones explícitas utilizando la clase<xref:System.Transactions.CommittableTransaction>.  
  
 Para consultar temas adicionales que traten sobre cómo escribir una aplicación transaccional, vea [Escribir una aplicación transaccional ](../../../../docs/framework/data/transactions/writing-a-transactional-application.md).  
  
### Implementar un administrador de recursos  
 Para implementar un administrador de recursos que pueda participar en una transacción, vea [Implementar un administrador de recursos ](../../../../docs/framework/data/transactions/implementing-a-resource-manager.md).En esta sección trata la inscripción de un recurso, la confirmación de transacciones, la recuperación después del error, y los procedimientos recomendados de la optimización.