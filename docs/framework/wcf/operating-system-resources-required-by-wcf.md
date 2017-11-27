---
title: Recursos del sistema operativo necesarios para WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6cfe114e5e044a6aaa1e356194a46b4a46011aa0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="a4a1e-102">Recursos del sistema operativo necesarios para WCF</span><span class="sxs-lookup"><span data-stu-id="a4a1e-102">Operating System Resources Required by WCF</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="a4a1e-103"> depende de varios recursos proporcionados por el sistema operativo para su funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="a4a1e-103"> depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="a4a1e-104">La tabla siguiente hace una lista de esos recursos.</span><span class="sxs-lookup"><span data-stu-id="a4a1e-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="a4a1e-105">Recurso</span><span class="sxs-lookup"><span data-stu-id="a4a1e-105">Resource</span></span>|<span data-ttu-id="a4a1e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4a1e-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a4a1e-107">Microsoft DTC (Coordinador de transacciones distribuidas) </span><span class="sxs-lookup"><span data-stu-id="a4a1e-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="a4a1e-108">Requerido para admitir las transacciones de OleTx.</span><span class="sxs-lookup"><span data-stu-id="a4a1e-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="a4a1e-109">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="a4a1e-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="a4a1e-110">Requerido si quiere usar IIS para hospedar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4a1e-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="a4a1e-111">Servicio de activación de procesos de Windows (WAS)</span><span class="sxs-lookup"><span data-stu-id="a4a1e-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="a4a1e-112">Requerido si desea utilizar WAS para hospedar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4a1e-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4a1e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4a1e-113">See Also</span></span>  
 [<span data-ttu-id="a4a1e-114">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="a4a1e-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
