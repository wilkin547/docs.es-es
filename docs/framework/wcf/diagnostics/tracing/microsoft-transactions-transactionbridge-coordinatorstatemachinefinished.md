---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 8cc32e7b38bfd1bdafd2377ad759f98b248d722e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710461"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a>Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
La máquina de estado para una inscripción del coordinador ha entrado en el estado finalizado.  
  
## <a name="description"></a>Descripción  
 Se realiza un seguimiento cuando el administrador de transacciones local crea que una inscripción del coordinador superior ha completado el procesamiento de 2pc. El resultado de la inscripción puede ser confirmado, anulado u olvidado. También se realiza un seguimiento si el administrador de transacciones local vota ReadOnly durante la preparación.  
  
## <a name="see-also"></a>Vea también
- [Traza](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)
