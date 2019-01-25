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
ms.openlocfilehash: d38b174a7e959647a9c1f5287b8acbbcdaf5ca7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564284"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="9c750-102">IGCHost::SetVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="9c750-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="9c750-103">Establece el tamaño máximo de memoria virtual de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9c750-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c750-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c750-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c750-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9c750-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="9c750-106">[in] El tamaño máximo en megabytes de memoria virtual de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9c750-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c750-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c750-107">Remarks</span></span>  
 <span data-ttu-id="9c750-108">El tamaño máximo de memoria virtual de tiempo de ejecución se puede cambiar dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="9c750-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c750-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c750-109">Requirements</span></span>  
 <span data-ttu-id="9c750-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c750-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c750-111">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="9c750-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="9c750-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9c750-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c750-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c750-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c750-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c750-114">See also</span></span>
- [<span data-ttu-id="9c750-115">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c750-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
