---
description: 'Más información acerca de: excepciones de transacción'
title: Excepciones en las transacciones
ms.date: 03/30/2017
ms.assetid: 1d27ed51-7eda-477f-9eca-94fa129f3e07
ms.openlocfilehash: edea932ca12fcd05994c979555e7eb9c0d00e969
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686068"
---
# <a name="transaction-exceptions"></a>Excepciones en las transacciones

En este tema se enumeran todas las excepciones generadas por Windows Communication Foundation transacción (WCF).  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|SFxCannotHaveDifferentTransactionProtocolsInOneBinding|La información de la directiva que se importa a partir de los metadatos especifica valores diferentes para TransactionProtocol entre las operaciones. Se admite solo un TransactionProtocol para cada punto de conexión.|  
|SFxTransactionAutoCompleteFalseAndInstanceContextMode|TransactionAutoComplete no puede ser falso a menos que el InstanceContextMode del servicio sea PerSession. Se encontró un error en la implementación del contrato y operación especificados.|  
|SFxTransactionInvalidSetTransactionComplete|Se puede llamar a OperationContext.SetTransactionComplete en una operación solo cuando TransactionAutoComplete está establecido como falso y TransactionScopeRequired está establecido como verdadero. Éste es un escenario no válido y se finalizó la transacción actual.|  
|TransactionFlowRequiredIssuedTokens|Para el flujo de una transacción, también deben admitirse los tokens emitidos del flujo.|  
|TrustDriverVersionDoesNotSupportIssuedTokens|La versión configurada de Trust no admite tokens emitidos. Utilice WSTrustFeb2005 o posterior.|
