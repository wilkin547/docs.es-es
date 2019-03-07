---
title: IGCHostControl::RequestVirtualMemLimit (Método)
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d163de5f2407d5b541573afe070db812d5980229
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474363"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="85a27-102">IGCHostControl::RequestVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="85a27-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="85a27-103">Solicita que el host para cambiar los límites de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="85a27-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85a27-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85a27-104">Syntax</span></span>  
  
```  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85a27-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85a27-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="85a27-106">[in] El tamaño solicitado de asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="85a27-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="85a27-107">[in, out] Un puntero al tamaño real de memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="85a27-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85a27-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85a27-108">Requirements</span></span>  
 <span data-ttu-id="85a27-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85a27-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85a27-110">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85a27-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85a27-111">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85a27-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85a27-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85a27-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a27-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="85a27-113">See also</span></span>
- [<span data-ttu-id="85a27-114">IGCHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85a27-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
