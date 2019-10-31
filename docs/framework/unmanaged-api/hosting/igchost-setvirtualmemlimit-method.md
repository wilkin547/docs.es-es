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
ms.openlocfilehash: c060e4883335a8318970b5fbd74bf72c9e13f5bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134861"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="9f6e2-102">IGCHost::SetVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="9f6e2-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="9f6e2-103">Establece el tamaño máximo de la memoria virtual del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9f6e2-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f6e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f6e2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f6e2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9f6e2-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="9f6e2-106">de Tamaño máximo, en megabytes, de la memoria virtual del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9f6e2-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f6e2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9f6e2-107">Remarks</span></span>  
 <span data-ttu-id="9f6e2-108">El tamaño máximo de la memoria virtual del tiempo de ejecución se puede cambiar dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="9f6e2-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f6e2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f6e2-109">Requirements</span></span>  
 <span data-ttu-id="9f6e2-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f6e2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f6e2-111">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="9f6e2-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="9f6e2-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9f6e2-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f6e2-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f6e2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f6e2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f6e2-114">See also</span></span>

- [<span data-ttu-id="9f6e2-115">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9f6e2-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
