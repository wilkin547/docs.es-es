---
title: Microsoft.Transactions.TransactionBridge.CreateTransactionFailure
ms.date: 03/30/2017
ms.assetid: c3468e23-49a9-4a84-972d-a79a658851b3
ms.openlocfilehash: 09b93ce4b72416cfea9f8c9850fd1e50c77035b7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270228"
---
# <a name="microsofttransactionstransactionbridgecreatetransactionfailure"></a>Microsoft.Transactions.TransactionBridge.CreateTransactionFailure

No se pudo crear una transacción.  
  
## <a name="description"></a>Descripción  

 Se genera este seguimiento cuando MSDTC no puede crear una transacción. Esto puede producirse como resultado de recursos insuficientes, espacio del registro insuficiente u otros errores.  
  
## <a name="troubleshooting"></a>Solución de problemas  

 Inspeccione la cadena de estado dentro del mensaje de seguimiento para determinar si existe cualquier elemento al que se le puede realizar alguna acción.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
