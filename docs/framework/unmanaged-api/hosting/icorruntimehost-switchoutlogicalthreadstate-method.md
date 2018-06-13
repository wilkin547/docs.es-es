---
title: ICorRuntimeHost::SwitchOutLogicalThreadState (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchOutLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff3bd9345825b5e7a4ccb41cd260b447b74cede3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437955"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="6185f-102">ICorRuntimeHost::SwitchOutLogicalThreadState (Método)</span><span class="sxs-lookup"><span data-stu-id="6185f-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="6185f-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="6185f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6185f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6185f-104">Syntax</span></span>  
  
```  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6185f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6185f-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="6185f-106">[out] Cookie que indica la fibra está desactivada.</span><span class="sxs-lookup"><span data-stu-id="6185f-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6185f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6185f-107">Requirements</span></span>  
 <span data-ttu-id="6185f-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6185f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6185f-109">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6185f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6185f-110">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6185f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6185f-111">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6185f-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6185f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6185f-112">See Also</span></span>  
 [<span data-ttu-id="6185f-113">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6185f-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
