---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: c398fc52d5924c033500b95924f9287b43cc9e9d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576608"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="134ae-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="134ae-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="134ae-103">Se anuló la transacción especificada porque estaba incompleta cuando se cerró la sesión y el TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute estaba establecido como false.</span><span class="sxs-lookup"><span data-stu-id="134ae-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="134ae-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="134ae-104">Description</span></span>  
 <span data-ttu-id="134ae-105">Se efectúa el seguimiento si la sesión activa actual se cerró, y no se completó la transacción y TransactionAutoCompleteOnSessionClose estaba establecido como `false`.</span><span class="sxs-lookup"><span data-stu-id="134ae-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="134ae-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="134ae-106">Troubleshooting</span></span>  
 <span data-ttu-id="134ae-107">Este seguimiento indica un error potencial de la aplicación que se debería investigar.</span><span class="sxs-lookup"><span data-stu-id="134ae-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="134ae-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="134ae-108">See also</span></span>

- [<span data-ttu-id="134ae-109">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="134ae-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="134ae-110">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="134ae-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="134ae-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="134ae-111">Administration and Diagnostics</span></span>](../index.md)
