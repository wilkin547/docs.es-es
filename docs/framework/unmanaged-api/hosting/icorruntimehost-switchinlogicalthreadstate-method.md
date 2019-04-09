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
ms.openlocfilehash: fc6cd8d2d0ab4648ad20392ef0968907917677e9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209495"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="067ca-102">ICorRuntimeHost::SwitchInLogicalThreadState (Método)</span><span class="sxs-lookup"><span data-stu-id="067ca-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="067ca-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="067ca-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="067ca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="067ca-104">Syntax</span></span>  
  
```  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="067ca-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="067ca-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="067ca-106">[in] Cookie que indica la fibra para usar.</span><span class="sxs-lookup"><span data-stu-id="067ca-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="067ca-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="067ca-107">Requirements</span></span>  
 <span data-ttu-id="067ca-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="067ca-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="067ca-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="067ca-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="067ca-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="067ca-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="067ca-111">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="067ca-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="067ca-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="067ca-112">See also</span></span>

- [<span data-ttu-id="067ca-113">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="067ca-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
