---
title: "Escribir una aplicaci&#243;n transaccional  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Escribir una aplicaci&#243;n transaccional 
Como un programador de la aplicación transaccional, puede tomar la ventaja de los dos modelos de programación proporcionados por el espacio de nombres <xref:System.Transactions> para crear una transacción.Puede utilizar un modelo de programación explícito utilizando la clase<xref:System.Transactions.Transaction>, o el modelo de programación implícito, en el cual las transacciones son gestionadas automáticamente por la infraestructura, utilizando la clase <xref:System.Transactions.TransactionScope> .Es muy recomendable utilizar el modelo de transacción implícito para el desarrollo.Puede encontrar más información sobre cómo utilizar un ambiente de transacción en el tema [Implementar una transacción implícita utilizando el ámbito de transacción ](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) .  
  
 Ambos modelos permiten confirmar una transacción cuando el programa llega a un estado coherente.Si la confirmación tiene éxito, se confirma la transacción de forma duradera.Si se produce un error en la confirmación, la transacción se anula.Si el programa de aplicación no puede completar correctamente la transacción, intenta anular y deshacer los efectos de la transacción.  
  
## En esta sección  
  
### Crear una transacción  
 El espacio de nombres <xref:System.Transactions> proporciona dos modelos para crear una transacción.Estos modelos se cubren en los temas siguientes.  
  
 [Implementar una transacción implícita utilizando el ámbito de transacción ](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Describe cómo el espacio de nombres <xref:System.Transactions> permite crear transacciones implícitas mediante la clase <xref:System.Transactions.TransactionScope>.  
  
 [Implementar una transacción explícita utilizando CommittableTransaction ](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Describe cómo el espacio de nombres <xref:System.Transactions> permite crear transacciones implícitas mediante la clase<xref:System.Transactions.CommittableTransaction>.  
  
### Extendiendo la administración de transacción  
 Cuando una transacción necesita tener acceso a un recurso en otro dominio de aplicación, o si desea dar de alta en otro administrador de recursos duradero, la transacción se realiza de manera escalonada automáticamente para ser administrada por MSDTC.El escalonado de la transacción se cubre en el tema [Extensión de administración de transacciones ](../../../../docs/framework/data/transactions/transaction-management-escalation.md) .  
  
### Simultaneidad  
 El tema [Administrar la simultaneidad con DependentTransaction ](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md) muestra cómo la simultaneidad se puede lograr entre las tareas asincrónicas utilizando la clase<xref:System.Transactions.DependentTransaction> .  
  
### Interoperabilidad COM\+  
 El tema [Interoperabilidad con transacciones de Enterprise Services y COM\+ ](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md) muestra cómo puede hacer sus transacciones distribuidas interactuar con transacciones de COM\+.  
  
### Diagnósticos  
 [Trazas de diagnóstico ](../../../../docs/framework/data/transactions/diagnostic-traces.md) describen cómo puede utilizar el seguimiento codifica que es generado por la infraestructura <xref:System.Transactions> para solucionar los errores en sus aplicaciones.  
  
### Funcionar dentro de ASP.NET  
 En el tema [Usar System.Transactions en ASP.NET](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md) se describe cómo puede utilizar correctamente <xref:System.Transactions> dentro de una aplicación ASP.NET.