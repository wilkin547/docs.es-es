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
# <a name="microsofttransactionstransactionbridgecreatetransactionfailure"></a><span data-ttu-id="3da20-102">Microsoft.Transactions.TransactionBridge.CreateTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="3da20-102">Microsoft.Transactions.TransactionBridge.CreateTransactionFailure</span></span>

<span data-ttu-id="3da20-103">No se pudo crear una transacción.</span><span class="sxs-lookup"><span data-stu-id="3da20-103">A transaction could not be created.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3da20-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="3da20-104">Description</span></span>  

 <span data-ttu-id="3da20-105">Se genera este seguimiento cuando MSDTC no puede crear una transacción.</span><span class="sxs-lookup"><span data-stu-id="3da20-105">This trace is generated when MSDTC is unable to create a transaction.</span></span> <span data-ttu-id="3da20-106">Esto puede producirse como resultado de recursos insuficientes, espacio del registro insuficiente u otros errores.</span><span class="sxs-lookup"><span data-stu-id="3da20-106">This can be due to low resources, insufficient log space, or other errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3da20-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="3da20-107">Troubleshooting</span></span>  

 <span data-ttu-id="3da20-108">Inspeccione la cadena de estado dentro del mensaje de seguimiento para determinar si existe cualquier elemento al que se le puede realizar alguna acción.</span><span class="sxs-lookup"><span data-stu-id="3da20-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da20-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3da20-109">See also</span></span>

- [<span data-ttu-id="3da20-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="3da20-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="3da20-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="3da20-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3da20-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3da20-112">Administration and Diagnostics</span></span>](../index.md)
