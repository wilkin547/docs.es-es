---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 3e4e1ff7ea8d8768c8d902dc09bd3b78646c2caf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256331"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="34228-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="34228-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>

<span data-ttu-id="34228-103">El servicio de protocolo WS-AT no pudo dar de alta en una transacción con el contexto de coordinación proporcionado.</span><span class="sxs-lookup"><span data-stu-id="34228-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="34228-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="34228-104">Description</span></span>  

 <span data-ttu-id="34228-105">Se realiza un seguimiento cuando MSDTC no puede dar de alta en una transacción para un protocolo 2pc concreto.</span><span class="sxs-lookup"><span data-stu-id="34228-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="34228-106">Esto puede ocurrir porque la transacción ya no existe, no se permite dar de alta ya o hay demasiadas inscripciones presentes.</span><span class="sxs-lookup"><span data-stu-id="34228-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="34228-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="34228-107">Troubleshooting</span></span>  

 <span data-ttu-id="34228-108">Inspeccione la cadena de estado dentro del mensaje de seguimiento para determinar si existe cualquier elemento al que se le puede realizar alguna acción.</span><span class="sxs-lookup"><span data-stu-id="34228-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34228-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="34228-109">See also</span></span>

- [<span data-ttu-id="34228-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="34228-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="34228-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="34228-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="34228-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="34228-112">Administration and Diagnostics</span></span>](../index.md)
