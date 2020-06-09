---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.date: 03/30/2017
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
ms.openlocfilehash: 0c53c1617f3aa3c5f16ba16e8ec548e46ce22137
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594340"
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
