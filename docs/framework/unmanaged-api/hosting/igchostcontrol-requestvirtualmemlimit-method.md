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
ms.openlocfilehash: bbcabdec45945b969230a40b85a62e24e323ccc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733937"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="0c6ea-102">IGCHostControl::RequestVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="0c6ea-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>

<span data-ttu-id="0c6ea-103">Solicita al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="0c6ea-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c6ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c6ea-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c6ea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c6ea-105">Parameters</span></span>  

 `sztMaxVirtualMemMB`  
 <span data-ttu-id="0c6ea-106">de Tamaño solicitado de memoria que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="0c6ea-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="0c6ea-107">[in, out] Puntero al tamaño real de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="0c6ea-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c6ea-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c6ea-108">Requirements</span></span>  

 <span data-ttu-id="0c6ea-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c6ea-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c6ea-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0c6ea-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c6ea-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c6ea-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c6ea-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c6ea-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c6ea-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c6ea-113">See also</span></span>

- [<span data-ttu-id="0c6ea-114">IGCHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c6ea-114">IGCHostControl Interface</span></span>](igchostcontrol-interface.md)
