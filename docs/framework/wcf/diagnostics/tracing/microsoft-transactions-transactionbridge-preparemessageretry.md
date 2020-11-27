---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.date: 03/30/2017
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
ms.openlocfilehash: d5ebe3e1ccce7a85073e2de19d915d116f709b2d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286973"
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a>Microsoft.Transactions.TransactionBridge.PrepareMessageRetry

Se envió un reintento de mensaje de preparación a un participante sin respuesta.  
  
## <a name="description"></a>Descripción  

 Se le hace un seguimiento si el Administrador de transacciones local necesitara reenviar un Mensaje de preparación a un participante subordinado porque no recibió respuesta en un período determinado de tiempo.  
  
## <a name="troubleshooting"></a>Solución de problemas  

 Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.  Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos. Ambos problemas pueden reducir drásticamente el rendimiento de las transacciones dentro del sistema.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
