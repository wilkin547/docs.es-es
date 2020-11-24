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
ms.openlocfilehash: 16f34d91861f9fcae51691ab13549bdf1ef333a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671504"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="a3fd9-102">ICorRuntimeHost::LocksHeldByLogicalThread (Método)</span><span class="sxs-lookup"><span data-stu-id="a3fd9-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>

<span data-ttu-id="a3fd9-103">Recupera el número de bloqueos que contiene el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a3fd9-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="a3fd9-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="a3fd9-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3fd9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3fd9-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3fd9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3fd9-106">Parameters</span></span>  

 `pCount`  
 <span data-ttu-id="a3fd9-107">enuncia Puntero al número de bloqueos que el subproceso actual contiene.</span><span class="sxs-lookup"><span data-stu-id="a3fd9-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3fd9-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3fd9-108">Requirements</span></span>  

 <span data-ttu-id="a3fd9-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3fd9-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3fd9-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a3fd9-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3fd9-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a3fd9-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3fd9-112">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="a3fd9-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3fd9-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3fd9-113">See also</span></span>

- [<span data-ttu-id="a3fd9-114">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3fd9-114">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
