---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 93c96d94aaeddeb7e7b04ea80645b8de95b0343e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666799"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="205bf-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="205bf-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="205bf-103">El servicio de protocolo WS-AT no pudo dar de alta en una transacción con el contexto de coordinación proporcionado.</span><span class="sxs-lookup"><span data-stu-id="205bf-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="205bf-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="205bf-104">Description</span></span>  
 <span data-ttu-id="205bf-105">Se realiza un seguimiento cuando MSDTC no puede dar de alta en una transacción para un protocolo 2pc concreto.</span><span class="sxs-lookup"><span data-stu-id="205bf-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="205bf-106">Esto puede ocurrir porque la transacción ya no existe, no se permite dar de alta ya o hay demasiadas inscripciones presentes.</span><span class="sxs-lookup"><span data-stu-id="205bf-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="205bf-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="205bf-107">Troubleshooting</span></span>  
 <span data-ttu-id="205bf-108">Inspeccione la cadena de estado dentro del mensaje de seguimiento para determinar si existe cualquier elemento al que se le puede realizar alguna acción.</span><span class="sxs-lookup"><span data-stu-id="205bf-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="205bf-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="205bf-109">See also</span></span>

- [<span data-ttu-id="205bf-110">Traza</span><span class="sxs-lookup"><span data-stu-id="205bf-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="205bf-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="205bf-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="205bf-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="205bf-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
