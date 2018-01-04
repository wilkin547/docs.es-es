---
title: IApartmentCallback (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IApartmentCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: IApartmentCallback
helpviewer_keywords: IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 821e19f9078f65941c1826c55abcfafb730fe0da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="6c928-102">IApartmentCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c928-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="6c928-103">Proporciona métodos para hacer que las devoluciones de llamada dentro de un apartamento.</span><span class="sxs-lookup"><span data-stu-id="6c928-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="6c928-104">Un *apartamento* es un contenedor lógico dentro de un proceso para los objetos que comparten los mismos requisitos de acceso de subproceso.</span><span class="sxs-lookup"><span data-stu-id="6c928-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6c928-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6c928-105">Methods</span></span>  
  
|<span data-ttu-id="6c928-106">Método</span><span class="sxs-lookup"><span data-stu-id="6c928-106">Method</span></span>|<span data-ttu-id="6c928-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c928-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6c928-108">DoCallback (método)</span><span class="sxs-lookup"><span data-stu-id="6c928-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="6c928-109">Ejecuta la función especificada dentro de un apartamento.</span><span class="sxs-lookup"><span data-stu-id="6c928-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c928-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c928-110">Requirements</span></span>  
 <span data-ttu-id="6c928-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c928-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c928-112">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6c928-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c928-113">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c928-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c928-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c928-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c928-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c928-115">See Also</span></span>  
 [<span data-ttu-id="6c928-116">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="6c928-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
