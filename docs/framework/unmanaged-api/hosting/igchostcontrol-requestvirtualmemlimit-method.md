---
title: "IGCHostControl::RequestVirtualMemLimit (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHostControl.RequestVirtualMemLimit
api_location: mscoree.dll
api_type: COM
f1_keywords: RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a14cb0d2d34db4ea0e5f9abf6fba6efc5e5a950c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="2746b-102">IGCHostControl::RequestVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="2746b-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="2746b-103">Solicita al host que cambie los límites de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="2746b-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2746b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2746b-104">Syntax</span></span>  
  
```  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2746b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2746b-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="2746b-106">[in] El tamaño solicitado de asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="2746b-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="2746b-107">[entrada, salida] Un puntero al tamaño real de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="2746b-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2746b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2746b-108">Requirements</span></span>  
 <span data-ttu-id="2746b-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2746b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2746b-110">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2746b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2746b-111">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2746b-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2746b-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2746b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2746b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2746b-113">See Also</span></span>  
 [<span data-ttu-id="2746b-114">IGCHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2746b-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
