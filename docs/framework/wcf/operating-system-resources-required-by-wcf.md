---
title: Recursos del sistema operativo necesarios para WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 759ab099066e300484860cf3f91d6d084ba1d339
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527086"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="88cae-102">Recursos del sistema operativo necesarios para WCF</span><span class="sxs-lookup"><span data-stu-id="88cae-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="88cae-103">Windows Communication Foundation (WCF) depende de varios recursos proporcionados por el sistema operativo para la función.</span><span class="sxs-lookup"><span data-stu-id="88cae-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="88cae-104">La tabla siguiente hace una lista de esos recursos.</span><span class="sxs-lookup"><span data-stu-id="88cae-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="88cae-105">Recurso</span><span class="sxs-lookup"><span data-stu-id="88cae-105">Resource</span></span>|<span data-ttu-id="88cae-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="88cae-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="88cae-107">Microsoft DTC (Coordinador de transacciones distribuidas) </span><span class="sxs-lookup"><span data-stu-id="88cae-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="88cae-108">Requerido para admitir las transacciones de OleTx.</span><span class="sxs-lookup"><span data-stu-id="88cae-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="88cae-109">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="88cae-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="88cae-110">Requerido si quiere usar IIS para hospedar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="88cae-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="88cae-111">Servicio de activación de procesos de Windows (WAS)</span><span class="sxs-lookup"><span data-stu-id="88cae-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="88cae-112">Requerido si desea utilizar WAS para hospedar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="88cae-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="88cae-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="88cae-113">See also</span></span>
- [<span data-ttu-id="88cae-114">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="88cae-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
