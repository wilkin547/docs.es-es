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
ms.openlocfilehash: d4814e44b1a5311cf6800c804df7a7e11000cbab
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805136"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="e25f5-102">IGCHostControl::RequestVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="e25f5-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="e25f5-103">Solicita al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="e25f5-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e25f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e25f5-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e25f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e25f5-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="e25f5-106">de Tamaño solicitado de memoria que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="e25f5-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="e25f5-107">[in, out] Puntero al tamaño real de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="e25f5-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e25f5-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e25f5-108">Requirements</span></span>  
 <span data-ttu-id="e25f5-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e25f5-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e25f5-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e25f5-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e25f5-111">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e25f5-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e25f5-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e25f5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e25f5-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e25f5-113">See also</span></span>

- [<span data-ttu-id="e25f5-114">IGCHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e25f5-114">IGCHostControl Interface</span></span>](igchostcontrol-interface.md)
