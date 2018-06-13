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
ms.openlocfilehash: d1d61c8aeaf458d8cbbd2976fa83aaa0eeb0f834
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437744"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="0a0e7-102">IGCHost::SetVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="0a0e7-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="0a0e7-103">Establece el tamaño máximo de memoria virtual de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0a0e7-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a0e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a0e7-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a0e7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a0e7-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="0a0e7-106">[in] El tamaño máximo, en megabytes, de la memoria virtual del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0a0e7-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a0e7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0a0e7-107">Remarks</span></span>  
 <span data-ttu-id="0a0e7-108">Pueden cambiar dinámicamente el tamaño máximo de memoria virtual de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0a0e7-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a0e7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a0e7-109">Requirements</span></span>  
 <span data-ttu-id="0a0e7-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a0e7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a0e7-111">**Encabezado:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="0a0e7-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="0a0e7-112">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a0e7-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a0e7-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a0e7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a0e7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a0e7-114">See Also</span></span>  
 [<span data-ttu-id="0a0e7-115">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a0e7-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
