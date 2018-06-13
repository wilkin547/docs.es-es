---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 7f376244343a75c16d5d2355642d626f666e42bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33483837"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="1831d-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="1831d-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="1831d-103">No se pudo completar la negociación protocolar OleTransactions para el contexto de coordinación especificado.</span><span class="sxs-lookup"><span data-stu-id="1831d-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1831d-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="1831d-104">Description</span></span>  
 <span data-ttu-id="1831d-105">Se le hace el seguimiento cuando una transacción entrante con información OleTx no puede usar la información OleTx adjunta, y volverá a utilizar en su lugar WS-AT.</span><span class="sxs-lookup"><span data-stu-id="1831d-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="1831d-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="1831d-106">Troubleshooting</span></span>  
 <span data-ttu-id="1831d-107">Indica un posible problema en la comunicación MSDTC RPC entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1831d-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="1831d-108">Si muchos de estos seguimientos aparecen en el registro, puede reducirse drásticamente el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1831d-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="1831d-109">Si no se desea OleTx, establezca `OleTxUpgradeEnabled` en 0 en la configuración de registro de WS-AT.</span><span class="sxs-lookup"><span data-stu-id="1831d-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1831d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1831d-110">See Also</span></span>  
 [<span data-ttu-id="1831d-111">Traza</span><span class="sxs-lookup"><span data-stu-id="1831d-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="1831d-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="1831d-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="1831d-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1831d-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
