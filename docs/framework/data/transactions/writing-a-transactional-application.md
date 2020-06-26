---
title: Crear una aplicación transaccional
description: Escriba una aplicación transaccional en .NET. Use un modelo de programación explícito o implícito con la clase de transacción o la clase TransactionScope, respectivamente.
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: 0235bb507d974e0bd3a7046ea213d8b78d870d59
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415776"
---
# <a name="writing-a-transactional-application"></a>Crear una aplicación transaccional
Como un programador de la aplicación transaccional, puede tomar la ventaja de los dos modelos de programación proporcionados por el espacio de nombres <xref:System.Transactions> para crear una transacción. Puede utilizar el modelo de programación explícito mediante la <xref:System.Transactions.Transaction> clase, o el modelo de programación implícito en el que la infraestructura administra automáticamente las transacciones, mediante la <xref:System.Transactions.TransactionScope> clase. Se recomienda utilizar el modelo de transacción implícita para el desarrollo. Puede encontrar más información sobre cómo usar un ámbito de transacción en el tema [implementación de una transacción implícita mediante el ámbito](implementing-an-implicit-transaction-using-transaction-scope.md) de la transacción.  
  
 Ambos modelos permiten confirmar una transacción cuando el programa llega a un estado coherente. Si la confirmación tiene éxito, se confirma la transacción de forma duradera. Si se produce un error en la confirmación, la transacción se anula. Si el programa de aplicación no puede completar correctamente la transacción, intenta anular y deshacer los efectos de la transacción.  
  
## <a name="in-this-section"></a>En esta sección  
  
### <a name="creating-a-transaction"></a>Crear una transacción  
 El espacio de nombres <xref:System.Transactions> proporciona dos modelos para crear una transacción. Estos modelos se cubren en los temas siguientes.  
  
 [Implementar una transacción implícita mediante el ámbito de la transacción](implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Describe cómo el espacio de nombres <xref:System.Transactions> permite crear transacciones implícitas mediante la clase <xref:System.Transactions.TransactionScope>.  
  
 [Implementar una transacción explícita mediante una transacción confirmable](implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Describe cómo el espacio de nombres <xref:System.Transactions> permite crear transacciones implícitas mediante la clase<xref:System.Transactions.CommittableTransaction>.  
  
### <a name="escalating-transaction-management"></a>Extendiendo la administración de transacción  
 Cuando una transacción necesita tener acceso a un recurso en otro dominio de aplicación, o si desea dar de alta en otro administrador de recursos duradero, la transacción se realiza de manera escalonada automáticamente para ser administrada por MSDTC. La extensión de la transacción se trata en el tema sobre [escalado](transaction-management-escalation.md) de la administración de transacciones.  
  
### <a name="concurrency"></a>Simultaneidad  
 El tema [administrar la simultaneidad con DependentTransaction](managing-concurrency-with-dependenttransaction.md) muestra cómo se puede lograr la simultaneidad entre tareas asincrónicas mediante la <xref:System.Transactions.DependentTransaction> clase.  
  
### <a name="com-interop"></a>Interoperabilidad COM+   
 El tema [interoperabilidad con Enterprise Services y transacciones de com+](interoperability-with-enterprise-services-and-com-transactions.md) muestra cómo puede hacer que las transacciones distribuidas interactúen con transacciones de com+.  
  
### <a name="diagnostics"></a>Diagnóstico  
 [Seguimientos de diagnóstico](diagnostic-traces.md) describe cómo puede usar los códigos de seguimiento generados por la <xref:System.Transactions> infraestructura de para solucionar errores en sus aplicaciones.  
  
### <a name="working-within-aspnet"></a>Funcionar dentro de ASP.NET  
 En el tema [uso de System. Transactions en ASP.net](using-system-transactions-in-aspnet.md) se describe cómo se puede usar correctamente <xref:System.Transactions> en una aplicación de ASP.net.
