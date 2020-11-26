---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: 9ad9dc9fd078f7ad4c0934c8bf9bb73feb935014
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236655"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a>Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt

El servicio de protocolo WS-AT recibió un mensaje Prepared o Repay desde un participante volátil desconocido. Se devolvió un error al participante, declara que el resultado de la transacción es dudoso.  
  
## <a name="description"></a>Descripción  

 Se realiza un seguimiento si el Administrador de transacciones local recibe un mensaje Prepared o Replay desde una inscripción volátil de la que ya se ha olvidado.  
  
## <a name="troubleshooting"></a>Solución de problemas  

 Investigue las causas potenciales de los últimos mensajes que proceden del participante volátil.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
