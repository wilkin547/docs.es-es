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
ms.openlocfilehash: 265ab5ae03b7b42c4f5f429df5d659d60e55f18e
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760724"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="e6f74-102">ICorRuntimeHost::LocksHeldByLogicalThread (Método)</span><span class="sxs-lookup"><span data-stu-id="e6f74-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="e6f74-103">Recupera el número de bloqueos que contiene el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e6f74-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="e6f74-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="e6f74-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6f74-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6f74-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6f74-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6f74-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="e6f74-107">enuncia Puntero al número de bloqueos que el subproceso actual contiene.</span><span class="sxs-lookup"><span data-stu-id="e6f74-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6f74-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6f74-108">Requirements</span></span>  
 <span data-ttu-id="e6f74-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6f74-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6f74-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e6f74-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6f74-111">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e6f74-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6f74-112">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e6f74-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f74-113">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="e6f74-113">See also</span></span>

- [<span data-ttu-id="e6f74-114">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6f74-114">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
