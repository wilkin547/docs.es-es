---
description: 'Más información acerca de: Microsoft. Transactions. TransactionBridge. VolatileOutcomeTimeout'
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: 5dd6ecce995d315581e1335e4dc83c425a6381b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677241"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a>Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout

El servicio de protocolo WS-AT superó el tiempo de espera de una respuesta a un mensaje de salida de un participante volátil. El resultado de la transacción puede estar en duda si el participante vuelve.  
  
## <a name="description"></a>Descripción  

 Se le hace seguimiento si un participante volátil ha decidido Confirmar o Anular, pero no ha respondido a una solicitud de confirmación o recuperación dentro de un período determinado de tiempo.  
  
## <a name="troubleshooting"></a>Solución de problemas  

 Asegúrese de que todos los participantes volátiles pueden responder dentro del período de tiempo dado. El período de tiempo predeterminado es de 180 segundos.  Si esto es insuficiente, aumente la directiva de temporizador `VolatileOutcomeDelay` para WS-AT.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
