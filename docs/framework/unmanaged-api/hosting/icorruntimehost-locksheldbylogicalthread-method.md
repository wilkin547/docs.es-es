---
description: 'Más información sobre: ICorRuntimeHost:: Locksheldbylogicalthread ((método)'
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
ms.openlocfilehash: bd64151bdc0c6aa0235192f0fc7f4badd8b0bbd6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789650"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="446d6-103">ICorRuntimeHost::LocksHeldByLogicalThread (Método)</span><span class="sxs-lookup"><span data-stu-id="446d6-103">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>

<span data-ttu-id="446d6-104">Recupera el número de bloqueos que contiene el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="446d6-104">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="446d6-105">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="446d6-105">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="446d6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="446d6-106">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="446d6-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="446d6-107">Parameters</span></span>  

 `pCount`  
 <span data-ttu-id="446d6-108">enuncia Puntero al número de bloqueos que el subproceso actual contiene.</span><span class="sxs-lookup"><span data-stu-id="446d6-108">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="446d6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="446d6-109">Requirements</span></span>  

 <span data-ttu-id="446d6-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="446d6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="446d6-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="446d6-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="446d6-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="446d6-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="446d6-113">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="446d6-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="446d6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="446d6-114">See also</span></span>

- [<span data-ttu-id="446d6-115">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="446d6-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
