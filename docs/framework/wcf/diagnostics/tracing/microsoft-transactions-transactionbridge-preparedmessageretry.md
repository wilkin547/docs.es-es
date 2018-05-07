---
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.date: 03/30/2017
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
ms.openlocfilehash: ba35f948143aff3de575e966aaec87f32f6f14b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a>Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
Se envió un reintento de mensaje preparado a un coordinador que no responde.  
  
## <a name="description"></a>Descripción  
 Se realiza un seguimiento en caso de que el administrador de transacciones local necesite volver a enviar un mensaje de “preparado” a un coordinador superior porque no recibió respuesta transcurrido cierto tiempo.  
  
## <a name="troubleshooting"></a>Solución de problemas  
 Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.  Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos. Ambos problemas reducirán drásticamente el rendimiento de las transacciones dentro del sistema.  
  
## <a name="see-also"></a>Vea también  
 [Traza](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)
