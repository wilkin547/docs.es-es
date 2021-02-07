---
description: 'Más información sobre: System. ServiceModel. TxFailedToNegotiateOleTx'
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: c7f18ef73ff9c09cc51ad3aa6c54c2bd672d0cc3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735574"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="2baae-103">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="2baae-103">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>

<span data-ttu-id="2baae-104">No se pudo completar la negociación protocolar OleTransactions para el contexto de coordinación especificado.</span><span class="sxs-lookup"><span data-stu-id="2baae-104">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2baae-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="2baae-105">Description</span></span>  

 <span data-ttu-id="2baae-106">Se le hace el seguimiento cuando una transacción entrante con información OleTx no puede usar la información OleTx adjunta, y volverá a utilizar en su lugar WS-AT.</span><span class="sxs-lookup"><span data-stu-id="2baae-106">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2baae-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="2baae-107">Troubleshooting</span></span>  

 <span data-ttu-id="2baae-108">Indica un posible problema en la comunicación MSDTC RPC entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2baae-108">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="2baae-109">Si muchos de estos seguimientos aparecen en el registro, puede reducirse drásticamente el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2baae-109">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="2baae-110">Si no se desea OleTx, establezca `OleTxUpgradeEnabled` en 0 en la configuración de registro de WS-AT.</span><span class="sxs-lookup"><span data-stu-id="2baae-110">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2baae-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2baae-111">See also</span></span>

- [<span data-ttu-id="2baae-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="2baae-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="2baae-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="2baae-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2baae-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2baae-114">Administration and Diagnostics</span></span>](../index.md)
