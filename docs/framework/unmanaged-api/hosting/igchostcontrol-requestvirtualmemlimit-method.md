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
ms.openlocfilehash: 948b18832ccfc5e0fc2e42ee58e6444a581de260
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209699"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="60851-102">IGCHostControl::RequestVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="60851-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="60851-103">Solicita que el host para cambiar los límites de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="60851-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60851-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60851-104">Syntax</span></span>  
  
```  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60851-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="60851-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="60851-106">[in] El tamaño solicitado de asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="60851-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="60851-107">[in, out] Un puntero al tamaño real de memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="60851-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60851-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60851-108">Requirements</span></span>  
 <span data-ttu-id="60851-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60851-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60851-110">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="60851-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60851-111">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60851-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60851-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60851-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60851-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="60851-113">See also</span></span>

- [<span data-ttu-id="60851-114">IGCHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="60851-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
