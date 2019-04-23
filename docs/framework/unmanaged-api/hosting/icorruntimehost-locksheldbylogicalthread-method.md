---
title: ICorRuntimeHost::LocksHeldByLogicalThread (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 90af015de4428f75330de89978a7fc0a4b26750b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144201"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="6160a-102">ICorRuntimeHost::LocksHeldByLogicalThread (Método)</span><span class="sxs-lookup"><span data-stu-id="6160a-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="6160a-103">Recupera el número de bloqueos que mantiene el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="6160a-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="6160a-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="6160a-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6160a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6160a-105">Syntax</span></span>  
  
```  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6160a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6160a-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="6160a-107">[out] Un puntero al número de bloqueos que mantiene el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="6160a-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6160a-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6160a-108">Requirements</span></span>  
 <span data-ttu-id="6160a-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6160a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6160a-110">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6160a-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6160a-111">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6160a-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6160a-112">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6160a-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6160a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6160a-113">See also</span></span>

- [<span data-ttu-id="6160a-114">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6160a-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
