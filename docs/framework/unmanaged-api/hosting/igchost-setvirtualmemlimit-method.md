---
title: IGCHost::SetVirtualMemLimit (Método)
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b25e9c738c95a918b79d3fd324787e4aaf3aaa7f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502480"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="87f2b-102">IGCHost::SetVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="87f2b-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="87f2b-103">Establece el tamaño máximo de memoria virtual de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="87f2b-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87f2b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87f2b-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87f2b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87f2b-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="87f2b-106">[in] El tamaño máximo en megabytes de memoria virtual de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="87f2b-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87f2b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="87f2b-107">Remarks</span></span>  
 <span data-ttu-id="87f2b-108">El tamaño máximo de memoria virtual de tiempo de ejecución se puede cambiar dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="87f2b-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87f2b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87f2b-109">Requirements</span></span>  
 <span data-ttu-id="87f2b-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87f2b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87f2b-111">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="87f2b-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="87f2b-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87f2b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87f2b-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87f2b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87f2b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="87f2b-114">See also</span></span>
- [<span data-ttu-id="87f2b-115">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87f2b-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
