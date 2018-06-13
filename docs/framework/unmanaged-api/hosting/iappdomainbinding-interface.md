---
title: IAppDomainBinding (Interfaz)
ms.date: 03/30/2017
api_name:
- IAppDomainBinding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainBinding
helpviewer_keywords:
- IAppDomainBinding interface [.NET Framework hosting]
ms.assetid: 368881ab-c4ea-4731-bf22-c596aac7c66c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6761ff204d299bc2db84e2e80d988306125a110
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430826"
---
# <a name="iappdomainbinding-interface"></a><span data-ttu-id="7ae05-102">IAppDomainBinding (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ae05-102">IAppDomainBinding Interface</span></span>
<span data-ttu-id="7ae05-103">Proporciona un método invocado por common language runtime (CLR) para notificar a la aplicación host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7ae05-103">Provides a method that is called by the common language runtime (CLR) to notify the host application that an application domain has been created.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ae05-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7ae05-104">Methods</span></span>  
  
|<span data-ttu-id="7ae05-105">Método</span><span class="sxs-lookup"><span data-stu-id="7ae05-105">Method</span></span>|<span data-ttu-id="7ae05-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ae05-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ae05-107">OnAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="7ae05-107">OnAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-onappdomain-method.md)|<span data-ttu-id="7ae05-108">Llamado por common language runtime (CLR) para notificar al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7ae05-108">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ae05-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ae05-109">Requirements</span></span>  
 <span data-ttu-id="7ae05-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ae05-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ae05-111">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7ae05-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7ae05-112">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7ae05-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ae05-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ae05-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ae05-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ae05-114">See Also</span></span>  
 [<span data-ttu-id="7ae05-115">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="7ae05-115">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
