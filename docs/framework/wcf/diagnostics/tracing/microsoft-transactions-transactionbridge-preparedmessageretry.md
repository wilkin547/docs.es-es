---
description: 'Más información acerca de: Microsoft. Transactions. TransactionBridge. PreparedMessageRetry'
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.date: 03/30/2017
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
ms.openlocfilehash: 99106493f0eec900875a713b439111fadb150c62
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677280"
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a>Microsoft.Transactions.TransactionBridge.PreparedMessageRetry

Se envió un reintento de mensaje preparado a un coordinador que no responde.  
  
## <a name="description"></a>Descripción  

 Se realiza un seguimiento en caso de que el administrador de transacciones local necesite volver a enviar un mensaje de “preparado” a un coordinador superior porque no recibió respuesta transcurrido cierto tiempo.  
  
## <a name="troubleshooting"></a>Solución de problemas  

 Investigue los posibles problemas de red o del producto que impiden la entrega puntual de la respuesta.  Si estos mensajes son frecuentes, puede indicar problemas de infraestructura o tiempos de respuesta anormalmente largos. Ambos problemas reducirán drásticamente el rendimiento de las transacciones dentro del sistema.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
