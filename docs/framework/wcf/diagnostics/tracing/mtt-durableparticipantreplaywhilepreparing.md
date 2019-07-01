---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 93354fbdd0c1726280526ca07a8b3dd1c57c8a25
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486769"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a>Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
El servicio de protocolo WS-AT recibió un mensaje de reproducción desde un participante duradero, que no respondió a la instrucción para preparar. Por consiguiente, se anuló la transacción.  
  
## <a name="description"></a>Descripción  
 Se realiza un seguimiento si se recibe un mensaje de reproducción mientras un participante duradero se está preparando. Se trata de un mensaje no válido para este estado y se va a anular la transacción.  
  
## <a name="troubleshooting"></a>Solución de problemas

Este error puede indicar que un participante duradero (incluidos los administradores de transacciones subordinados) se ha recuperado del error; Sin embargo, es seguro del resultado de la transacción y solicita su estado.  
  
## <a name="see-also"></a>Vea también

- [Traza](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)
