---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 3b9a3703e49c3932f62fcfb6994c9028b074bbe8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594418"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a>Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
La máquina de estado para una inscripción del coordinador ha entrado en el estado finalizado.  
  
## <a name="description"></a>Descripción  
 Se realiza un seguimiento cuando el administrador de transacciones local crea que una inscripción del coordinador superior ha completado el procesamiento de 2pc. El resultado de la inscripción puede ser confirmado, anulado u olvidado. También se realiza un seguimiento si el administrador de transacciones local vota ReadOnly durante la preparación.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
