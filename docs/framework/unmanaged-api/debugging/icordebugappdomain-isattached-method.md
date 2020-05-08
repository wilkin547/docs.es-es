---
title: ICorDebugAppDomain::IsAttached (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
ms.openlocfilehash: a2f6df7647ffe9f2adff963b6629ed29ece053c0
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895157"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="fb547-102">ICorDebugAppDomain::IsAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="fb547-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="fb547-103">Obtiene un valor que indica si el depurador está asociado al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="fb547-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb547-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb547-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb547-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb547-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="fb547-106">enuncia `true` si el depurador está asociado al dominio de aplicación; en caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="fb547-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb547-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fb547-107">Remarks</span></span>  
 <span data-ttu-id="fb547-108">Los métodos ICorDebugController no se pueden usar hasta que el depurador se asocie al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="fb547-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb547-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb547-109">Requirements</span></span>  
 <span data-ttu-id="fb547-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb547-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb547-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb547-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb547-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb547-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb547-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb547-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
