---
title: Excepciones en las transacciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d27ed51-7eda-477f-9eca-94fa129f3e07
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f13a39c251afd55dbb1f0d2dde4fc66fe38d30a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="transaction-exceptions"></a>Excepciones en las transacciones
En este tema se enumeran todas las excepciones generadas por la transacción [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|SFxCannotHaveDifferentTransactionProtocolsInOneBinding|La información de la directiva que se importa a partir de los metadatos especifica valores diferentes para TransactionProtocol entre las operaciones. Se admite solo un TransactionProtocol para cada extremo.|  
|SFxTransactionAutoCompleteFalseAndInstanceContextMode|TransactionAutoComplete no puede ser falso a menos que el InstanceContextMode del servicio sea PerSession. Se encontró un error en la implementación del contrato y operación especificados.|  
|SFxTransactionInvalidSetTransactionComplete|Se puede llamar a OperationContext.SetTransactionComplete en una operación solo cuando TransactionAutoComplete está establecido como falso y TransactionScopeRequired está establecido como verdadero. Éste es un escenario no válido y se finalizó la transacción actual.|  
|TransactionFlowRequiredIssuedTokens|Para el flujo de una transacción, también deben admitirse los tokens emitidos del flujo.|  
|TrustDriverVersionDoesNotSupportIssuedTokens|La versión configurada de Trust no admite tokens emitidos. Utilice WSTrustFeb2005 o posterior.|
