---
title: Características proporcionadas por System.Transactions
description: Revise las características proporcionadas por el espacio de nombres System. Transactions en .NET para escribir su propia aplicación de transacción y administrador de recursos.
ms.date: 03/30/2017
ms.assetid: e458cef9-63b5-4401-b448-1536dcd9d9e5
ms.openlocfilehash: 27c6224530b4faa1ada93db8147f9334f38b93ab
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91182927"
---
# <a name="features-provided-by-systemtransactions"></a>Características proporcionadas por System.Transactions

En esta sección se describe cómo se pueden utilizar las características proporcionadas por el espacio de nombres <xref:System.Transactions> para escribir su propia aplicación transaccional y administrador de recursos. Específicamente, esta sección trata de cómo crear y participar en una transacción (local o distribuida) con uno o varios participantes.  
  
## <a name="overview-of-systemtransactions"></a>Información general sobre System.Transactions  

 La infraestructura proporcionada por las clases en el espacio de nombres <xref:System.Transactions> hace que la programación transaccional sea sencilla y eficaz en toda la plataforma al admitir las transacciones iniciadas en SQL Server, ADO.NET, Message Queuing (MSMQ) y MSDTC (Coordinador de transacciones distribuidas de Microsoft). El espacio de nombres <xref:System.Transactions> proporciona un modelo de programación explícito según la clase <xref:System.Transactions.Transaction>, así como un modelo de programación implícito utilizando la clase <xref:System.Transactions.TransactionScope>, en la que la infraestructura administra automáticamente las transacciones. Para obtener más información sobre cómo crear una aplicación transaccional con estos dos modelos, vea [escribir una aplicación transaccional](writing-a-transactional-application.md).  
  
 El espacio de nombres <xref:System.Transactions> también proporciona tipos para implementar un administrador de recursos. Un administrador de recursos administra los datos duraderos o volátiles que se utilizan en una transacción, y trabaja en cooperación con el administrador de transacciones para dotar a la aplicación de una garantía de atomicidad y aislamiento. El administrador de transacciones que proporciona la infraestructura <xref:System.Transactions> admite transacciones que implican varios recursos volátiles o un recurso duradero único. Para obtener más información sobre cómo implementar un administrador de recursos, consulte [implementación de un administrador de recursos](implementing-a-resource-manager.md).  
  
 Cuando un administrador de recursos duraderos adicional se da de alta a sí mismo en una transacción, el administrador de transacciones también dirige de forma transparente las transacciones locales a transacciones distribuidas, coordinando con un administrador de transacciones basado en disco como DTC. La infraestructura <xref:System.Transactions> proporciona un rendimiento mejorado principalmente de dos formas:  
  
- Subida dinámica, que asegura que la infraestructura <xref:System.Transactions> solo activa el MSDTC cuando una transacción abarca varios recursos distribuidos. Para obtener más información sobre la elevación dinámica. Vea el tema sobre [escalado de administración de transacciones](transaction-management-escalation.md) .  
  
- Inscripciones de ascenso, que permiten que un recurso, como una base de datos, asuma la propiedad de la transacción si es la única entidad que participa en la transacción. Posteriormente, si resulta necesario, la infraestructura <xref:System.Transactions> aún puede dirigir la administración de la transacción a la MSDTC. Esto reduce aún más la oportunidad de utilizar MSDTC. Las inlistas que se pueden promover se describen en profundidad en el tema[optimización mediante la confirmación de fase única y la notificación de fase única promocionable](optimization-spc-and-promotable-spn.md).  
  
 El espacio de nombres <xref:System.Transactions> define tres niveles de confianza - AllowPartiallyTrustedCallers (APTCA), DistributedTransactionPermission (DTP) y plena confianza - que restringe el acceso a los tipos de recursos que expone. Para obtener más información sobre los distintos niveles de confianza, vea [niveles de confianza de seguridad en el acceso a recursos](security-trust-levels-in-accessing-resources.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
### <a name="writing-a-transactional-application"></a>Crear una aplicación transaccional  

 El espacio de nombres <xref:System.Transactions> proporciona dos modelos para crear aplicaciones transaccionales. [Implementar una transacción implícita mediante el ámbito](implementing-an-implicit-transaction-using-transaction-scope.md) de la transacción describe cómo el <xref:System.Transactions> espacio de nombres permite crear transacciones implícitas mediante la <xref:System.Transactions.TransactionScope> clase.  
  
 La [implementación de una transacción explícita mediante CommittableTransaction](implementing-an-explicit-transaction-using-committabletransaction.md) describe cómo el <xref:System.Transactions> espacio de nombres admite la creación de transacciones explícitas mediante la <xref:System.Transactions.CommittableTransaction> clase.  
  
 Para más información sobre cómo escribir una aplicación transaccional, consulte [escribir una aplicación transaccional](writing-a-transactional-application.md).  
  
### <a name="implementing-a-resource-manager"></a>Implementar un administrador de recursos  

 Para implementar un administrador de recursos que puede participar en una transacción, vea [implementar un administrador de recursos](implementing-a-resource-manager.md). En esta sección trata la inscripción de un recurso, la confirmación de transacciones, la recuperación después del error, y los procedimientos recomendados de la optimización.
