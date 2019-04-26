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
ms.openlocfilehash: b5b4210bda7d41b190f1025b62132c5df896a2a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703626"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="ccf5b-102">IGCHost::SetVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="ccf5b-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="ccf5b-103">Establece el tamaño máximo de memoria virtual de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ccf5b-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccf5b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccf5b-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccf5b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ccf5b-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="ccf5b-106">[in] El tamaño máximo en megabytes de memoria virtual de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ccf5b-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccf5b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ccf5b-107">Remarks</span></span>  
 <span data-ttu-id="ccf5b-108">El tamaño máximo de memoria virtual de tiempo de ejecución se puede cambiar dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="ccf5b-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccf5b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccf5b-109">Requirements</span></span>  
 <span data-ttu-id="ccf5b-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccf5b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccf5b-111">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="ccf5b-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="ccf5b-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ccf5b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccf5b-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccf5b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf5b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccf5b-114">See also</span></span>

- [<span data-ttu-id="ccf5b-115">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccf5b-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
