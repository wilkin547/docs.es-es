---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 6aecc8f808d42c0096f6caef0574c72db6c53079
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528672"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="7e9fa-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="7e9fa-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="7e9fa-103">No se pudo completar la negociación protocolar OleTransactions para el contexto de coordinación especificado.</span><span class="sxs-lookup"><span data-stu-id="7e9fa-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7e9fa-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e9fa-104">Description</span></span>  
 <span data-ttu-id="7e9fa-105">Se le hace el seguimiento cuando una transacción entrante con información OleTx no puede usar la información OleTx adjunta, y volverá a utilizar en su lugar WS-AT.</span><span class="sxs-lookup"><span data-stu-id="7e9fa-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="7e9fa-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="7e9fa-106">Troubleshooting</span></span>  
 <span data-ttu-id="7e9fa-107">Indica un posible problema en la comunicación MSDTC RPC entre equipos.</span><span class="sxs-lookup"><span data-stu-id="7e9fa-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="7e9fa-108">Si muchos de estos seguimientos aparecen en el registro, puede reducirse drásticamente el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7e9fa-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="7e9fa-109">Si no se desea OleTx, establezca `OleTxUpgradeEnabled` en 0 en la configuración de registro de WS-AT.</span><span class="sxs-lookup"><span data-stu-id="7e9fa-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e9fa-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e9fa-110">See also</span></span>
- [<span data-ttu-id="7e9fa-111">Traza</span><span class="sxs-lookup"><span data-stu-id="7e9fa-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="7e9fa-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="7e9fa-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7e9fa-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="7e9fa-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
