---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61360eff4f2c403eea98bbc0a2eae36e516b3d7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="50c31-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="50c31-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="50c31-103">No se pudo completar la negociación protocolar OleTransactions para el contexto de coordinación especificado.</span><span class="sxs-lookup"><span data-stu-id="50c31-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="50c31-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="50c31-104">Description</span></span>  
 <span data-ttu-id="50c31-105">Se le hace el seguimiento cuando una transacción entrante con información OleTx no puede usar la información OleTx adjunta, y volverá a utilizar en su lugar WS-AT.</span><span class="sxs-lookup"><span data-stu-id="50c31-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="50c31-106">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="50c31-106">Troubleshooting</span></span>  
 <span data-ttu-id="50c31-107">Indica un posible problema en la comunicación MSDTC RPC entre equipos.</span><span class="sxs-lookup"><span data-stu-id="50c31-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="50c31-108">Si muchos de estos seguimientos aparecen en el registro, puede reducirse drásticamente el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="50c31-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="50c31-109">Si no se desea OleTx, establezca `OleTxUpgradeEnabled` en 0 en la configuración de registro de WS-AT.</span><span class="sxs-lookup"><span data-stu-id="50c31-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c31-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="50c31-110">See Also</span></span>  
 [<span data-ttu-id="50c31-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="50c31-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="50c31-112">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="50c31-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="50c31-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="50c31-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
