---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 742e80a3115e8f8caa728e0d8c460ee8b964ddc9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84588722"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a>Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
El servicio de protocolo WS-AT no pudo dar de alta en una transacción con el contexto de coordinación proporcionado.  
  
## <a name="description"></a>Descripción  
 Se realiza un seguimiento cuando MSDTC no puede dar de alta en una transacción para un protocolo 2pc concreto.  Esto puede ocurrir porque la transacción ya no existe, no se permite dar de alta ya o hay demasiadas inscripciones presentes.  
  
## <a name="troubleshooting"></a>Solución de problemas  
 Inspeccione la cadena de estado dentro del mensaje de seguimiento para determinar si existe cualquier elemento al que se le puede realizar alguna acción.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
