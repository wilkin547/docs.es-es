---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 7b1f6a2f4a344b566c76d0095942b84a8a4e76f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166509"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a>System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
Se anuló la transacción especificada porque estaba incompleta cuando se cerró la sesión y el TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute estaba establecido como false.  
  
## <a name="description"></a>Descripción  
 Se efectúa el seguimiento si la sesión activa actual se cerró, y no se completó la transacción y TransactionAutoCompleteOnSessionClose estaba establecido como `false`.  
  
## <a name="troubleshooting"></a>Solución de problemas  
 Este seguimiento indica un error potencial de la aplicación que se debería investigar.  
  
## <a name="see-also"></a>Vea también

- [Traza](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)
