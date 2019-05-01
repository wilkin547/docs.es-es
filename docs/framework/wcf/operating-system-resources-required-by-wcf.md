---
title: Recursos del sistema operativo necesarios para WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 828d656370efd7638fa4cf367b84ee7b316b89bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955225"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="479d5-102">Recursos del sistema operativo necesarios para WCF</span><span class="sxs-lookup"><span data-stu-id="479d5-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="479d5-103">Windows Communication Foundation (WCF) depende de varios recursos proporcionados por el sistema operativo para la función.</span><span class="sxs-lookup"><span data-stu-id="479d5-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="479d5-104">La tabla siguiente hace una lista de esos recursos.</span><span class="sxs-lookup"><span data-stu-id="479d5-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="479d5-105">Recurso</span><span class="sxs-lookup"><span data-stu-id="479d5-105">Resource</span></span>|<span data-ttu-id="479d5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="479d5-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="479d5-107">Microsoft DTC (Coordinador de transacciones distribuidas) </span><span class="sxs-lookup"><span data-stu-id="479d5-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="479d5-108">Requerido para admitir las transacciones de OleTx.</span><span class="sxs-lookup"><span data-stu-id="479d5-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="479d5-109">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="479d5-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="479d5-110">Requerido si quiere usar IIS para hospedar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="479d5-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="479d5-111">Servicio de activación de procesos de Windows (WAS)</span><span class="sxs-lookup"><span data-stu-id="479d5-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="479d5-112">Requerido si desea utilizar WAS para hospedar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="479d5-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="479d5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="479d5-113">See also</span></span>

- [<span data-ttu-id="479d5-114">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="479d5-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
