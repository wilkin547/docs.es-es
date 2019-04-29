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
ms.openlocfilehash: 1291d4e69843db7bd90af07291da415220d98807
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700298"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="29f37-102">ICorRuntimeHost::SwitchOutLogicalThreadState (Método)</span><span class="sxs-lookup"><span data-stu-id="29f37-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="29f37-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="29f37-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29f37-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29f37-104">Syntax</span></span>  
  
```  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29f37-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="29f37-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="29f37-106">[out] Cookie que indica la fibra está saliendo.</span><span class="sxs-lookup"><span data-stu-id="29f37-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29f37-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29f37-107">Requirements</span></span>  
 <span data-ttu-id="29f37-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29f37-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29f37-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="29f37-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29f37-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="29f37-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29f37-111">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="29f37-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29f37-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="29f37-112">See also</span></span>

- [<span data-ttu-id="29f37-113">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="29f37-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
