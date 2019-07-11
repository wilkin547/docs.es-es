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
ms.openlocfilehash: cbb0b6191c74c2b7ebdc8267701f246c17b016f9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779524"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="857dd-102">IGCHostControl::RequestVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="857dd-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="857dd-103">Solicita que el host para cambiar los límites de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="857dd-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="857dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="857dd-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="857dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="857dd-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="857dd-106">[in] El tamaño solicitado de asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="857dd-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="857dd-107">[in, out] Un puntero al tamaño real de memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="857dd-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="857dd-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="857dd-108">Requirements</span></span>  
 <span data-ttu-id="857dd-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="857dd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="857dd-110">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="857dd-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="857dd-111">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="857dd-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="857dd-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="857dd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="857dd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="857dd-113">See also</span></span>

- [<span data-ttu-id="857dd-114">IGCHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="857dd-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
