---
title: Crear una aplicación transaccional
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: 048df434ff0ada2ab5f8c7473913f6c34c05d1a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357203"
---
# <a name="writing-a-transactional-application"></a>Crear una aplicación transaccional
Como un programador de la aplicación transaccional, puede tomar la ventaja de los dos modelos de programación proporcionados por el espacio de nombres <xref:System.Transactions> para crear una transacción. Puede utilizar el modelo de programación explícito mediante el uso de la <xref:System.Transactions.Transaction> clase o el modelo de programación implícito en el que las transacciones se administran automáticamente por la infraestructura, mediante el uso de la <xref:System.Transactions.TransactionScope> clase. Se recomienda que utilice el modelo de transacción implícita para el desarrollo. Puede encontrar más información sobre cómo utilizar un ámbito de transacción en el [implementar una transacción implícita con ámbito de transacción](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) tema.  
  
 Ambos modelos permiten confirmar una transacción cuando el programa llega a un estado coherente. Si la confirmación tiene éxito, se confirma la transacción de forma duradera. Si se produce un error en la confirmación, la transacción se anula. Si el programa de aplicación no puede completar correctamente la transacción, intenta anular y deshacer los efectos de la transacción.  
  
## <a name="in-this-section"></a>En esta sección  
  
### <a name="creating-a-transaction"></a>Crear una transacción  
 El espacio de nombres <xref:System.Transactions> proporciona dos modelos para crear una transacción. Estos modelos se cubren en los temas siguientes.  
  
 [Implementación de una transacción implícita mediante el ámbito de transacción](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Describe cómo el espacio de nombres <xref:System.Transactions> permite crear transacciones implícitas mediante la clase <xref:System.Transactions.TransactionScope>.  
  
 [Implementación de una transacción explícita con CommittableTransaction](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Describe cómo el espacio de nombres <xref:System.Transactions> permite crear transacciones implícitas mediante la clase<xref:System.Transactions.CommittableTransaction>.  
  
### <a name="escalating-transaction-management"></a>Extendiendo la administración de transacción  
 Cuando una transacción necesita tener acceso a un recurso en otro dominio de aplicación, o si desea dar de alta en otro administrador de recursos duradero, la transacción se realiza de manera escalonada automáticamente para ser administrada por MSDTC. Extensión de transacciones se trata en la [Transaction Management Escalation](../../../../docs/framework/data/transactions/transaction-management-escalation.md) tema.  
  
### <a name="concurrency"></a>simultaneidad  
 El tema [Managing Concurrency with DependentTransaction](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md) muestra cómo se puede lograr la simultaneidad entre las tareas asincrónicas mediante el uso de la <xref:System.Transactions.DependentTransaction> clase.  
  
### <a name="com-interop"></a>Interoperabilidad COM+  
 El tema [interoperabilidad con servicios empresariales y las transacciones COM +](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md) muestra cómo se pueden hacer que las transacciones distribuidas interactuar con las transacciones COM +.  
  
### <a name="diagnostics"></a>Diagnóstico  
 [Seguimientos de diagnóstico](../../../../docs/framework/data/transactions/diagnostic-traces.md) describe cómo puede utilizar los códigos de seguimiento generados por el <xref:System.Transactions> infraestructura para solucionar los errores en las aplicaciones.  
  
### <a name="working-within-aspnet"></a>Funcionar dentro de ASP.NET  
 El [usar System.Transactions en ASP.NET](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md) tema describe cómo puede usar correctamente <xref:System.Transactions> dentro de una aplicación de ASP.NET.
