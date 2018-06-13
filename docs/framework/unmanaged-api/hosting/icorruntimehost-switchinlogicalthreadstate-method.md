---
title: ICorRuntimeHost::SwitchInLogicalThreadState (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0836d47c364a815ea3de9b991fe788815a1b36c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436694"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="c261d-102">ICorRuntimeHost::SwitchInLogicalThreadState (Método)</span><span class="sxs-lookup"><span data-stu-id="c261d-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="c261d-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="c261d-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c261d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c261d-104">Syntax</span></span>  
  
```  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c261d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c261d-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="c261d-106">[in] Cookie que indica la fibra para usar.</span><span class="sxs-lookup"><span data-stu-id="c261d-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c261d-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c261d-107">Requirements</span></span>  
 <span data-ttu-id="c261d-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c261d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c261d-109">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c261d-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c261d-110">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c261d-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c261d-111">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="c261d-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c261d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c261d-112">See Also</span></span>  
 [<span data-ttu-id="c261d-113">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c261d-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
