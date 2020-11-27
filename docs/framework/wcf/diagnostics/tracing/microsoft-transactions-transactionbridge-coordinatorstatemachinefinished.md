---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 2d874cebe96b9caa99032e2881e19ec9cd34d047
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259016"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a>Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished

La máquina de estado para una inscripción del coordinador ha entrado en el estado finalizado.  
  
## <a name="description"></a>Descripción  

 Se realiza un seguimiento cuando el administrador de transacciones local crea que una inscripción del coordinador superior ha completado el procesamiento de 2pc. El resultado de la inscripción puede ser confirmado, anulado u olvidado. También se realiza un seguimiento si el administrador de transacciones local vota ReadOnly durante la preparación.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
