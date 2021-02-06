---
description: 'Más información acerca de: Microsoft. Transactions. TransactionBridge. DurableParticipantReplayWhilePreparing'
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: fcaa50dd4faa548cad8ff085f1c66f94c63bd010
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99635667"
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
