---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 2de1aa51d58d9d86f953e027fd3f7f172e3887d3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097569"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a>System.ServiceModel.TxFailedToNegotiateOleTx
No se pudo completar la negociación protocolar OleTransactions para el contexto de coordinación especificado.  
  
## <a name="description"></a>Descripción  
 Se le hace el seguimiento cuando una transacción entrante con información OleTx no puede usar la información OleTx adjunta, y volverá a utilizar en su lugar WS-AT.  
  
## <a name="troubleshooting"></a>Solución de problemas  
 Indica un posible problema en la comunicación MSDTC RPC entre equipos. Si muchos de estos seguimientos aparecen en el registro, puede reducirse drásticamente el rendimiento.  Si no se desea OleTx, establezca `OleTxUpgradeEnabled` en 0 en la configuración de registro de WS-AT.  
  
## <a name="see-also"></a>Vea también

- [Traza](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)
