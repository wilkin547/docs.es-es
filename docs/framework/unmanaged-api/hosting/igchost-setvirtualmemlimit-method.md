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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088397"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="bad66-102">IGCHost::SetVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="bad66-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="bad66-103">Establece el tamaño máximo de memoria virtual de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bad66-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bad66-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bad66-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bad66-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="bad66-106">[in] El tamaño máximo en megabytes de memoria virtual de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bad66-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bad66-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bad66-107">Remarks</span></span>  
 <span data-ttu-id="bad66-108">El tamaño máximo de memoria virtual de tiempo de ejecución se puede cambiar dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="bad66-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bad66-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bad66-109">Requirements</span></span>  
 <span data-ttu-id="bad66-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bad66-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bad66-111">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="bad66-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="bad66-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bad66-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="bad66-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bad66-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bad66-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bad66-114">See also</span></span>

- [<span data-ttu-id="bad66-115">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bad66-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
