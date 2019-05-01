---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 7b1f6a2f4a344b566c76d0095942b84a8a4e76f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991632"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="0a6e5-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="0a6e5-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="0a6e5-103">Se anuló la transacción especificada porque estaba incompleta cuando se cerró la sesión y el TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute estaba establecido como false.</span><span class="sxs-lookup"><span data-stu-id="0a6e5-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0a6e5-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="0a6e5-104">Description</span></span>  
 <span data-ttu-id="0a6e5-105">Se efectúa el seguimiento si la sesión activa actual se cerró, y no se completó la transacción y TransactionAutoCompleteOnSessionClose estaba establecido como `false`.</span><span class="sxs-lookup"><span data-stu-id="0a6e5-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="0a6e5-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="0a6e5-106">Troubleshooting</span></span>  
 <span data-ttu-id="0a6e5-107">Este seguimiento indica un error potencial de la aplicación que se debería investigar.</span><span class="sxs-lookup"><span data-stu-id="0a6e5-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a6e5-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a6e5-108">See also</span></span>

- [<span data-ttu-id="0a6e5-109">Traza</span><span class="sxs-lookup"><span data-stu-id="0a6e5-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="0a6e5-110">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="0a6e5-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0a6e5-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="0a6e5-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
