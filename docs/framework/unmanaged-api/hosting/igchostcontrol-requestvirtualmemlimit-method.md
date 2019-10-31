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
ms.openlocfilehash: ccff575974093de0bf00b257cba78c509f9cbd92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134775"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="84a67-102">IGCHostControl::RequestVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="84a67-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="84a67-103">Solicita al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="84a67-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84a67-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84a67-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84a67-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="84a67-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="84a67-106">de Tamaño solicitado de memoria que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="84a67-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="84a67-107">[in, out] Puntero al tamaño real de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="84a67-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84a67-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84a67-108">Requirements</span></span>  
 <span data-ttu-id="84a67-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84a67-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84a67-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="84a67-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84a67-111">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="84a67-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84a67-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84a67-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a67-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="84a67-113">See also</span></span>

- [<span data-ttu-id="84a67-114">IGCHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="84a67-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
