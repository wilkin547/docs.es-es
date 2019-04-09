---
title: Recursos del sistema operativo necesarios para WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 828d656370efd7638fa4cf367b84ee7b316b89bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100956"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="d06da-102">Recursos del sistema operativo necesarios para WCF</span><span class="sxs-lookup"><span data-stu-id="d06da-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="d06da-103">Windows Communication Foundation (WCF) depende de varios recursos proporcionados por el sistema operativo para la función.</span><span class="sxs-lookup"><span data-stu-id="d06da-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="d06da-104">La tabla siguiente hace una lista de esos recursos.</span><span class="sxs-lookup"><span data-stu-id="d06da-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="d06da-105">Recurso</span><span class="sxs-lookup"><span data-stu-id="d06da-105">Resource</span></span>|<span data-ttu-id="d06da-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d06da-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="d06da-107">Microsoft DTC (Coordinador de transacciones distribuidas) </span><span class="sxs-lookup"><span data-stu-id="d06da-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="d06da-108">Requerido para admitir las transacciones de OleTx.</span><span class="sxs-lookup"><span data-stu-id="d06da-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="d06da-109">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="d06da-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="d06da-110">Requerido si quiere usar IIS para hospedar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="d06da-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="d06da-111">Servicio de activación de procesos de Windows (WAS)</span><span class="sxs-lookup"><span data-stu-id="d06da-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="d06da-112">Requerido si desea utilizar WAS para hospedar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="d06da-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d06da-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d06da-113">See also</span></span>

- [<span data-ttu-id="d06da-114">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="d06da-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
