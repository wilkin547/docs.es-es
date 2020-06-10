---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 31fb8d466c76c7490aa80dfcab089332af4036a2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589137"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a>Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
El servicio de protocolo WS-AT recibió un mensaje de reproducción desde un participante duradero, que no respondió a la instrucción para preparar. Por consiguiente, se anuló la transacción.  
  
## <a name="description"></a>Descripción  
 Se realiza un seguimiento si se recibe un mensaje de reproducción mientras un participante duradero se está preparando. Se trata de un mensaje no válido para este estado y se va a anular la transacción.  
  
## <a name="troubleshooting"></a>Solución de problemas

Recibir este error puede indicar que un participante duradero (incluido el TransactionManagers subordinado) se ha recuperado de un error. sin embargo, no está seguro del resultado de la transacción y solicita su estado.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
