---
title: ICorDebugAssembly2::IsFullyTrusted (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
ms.openlocfilehash: 8a2a6be0db76f5ee2c7fa67c2038e0a5c845bd0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719715"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="60295-102">ICorDebugAssembly2::IsFullyTrusted (Método)</span><span class="sxs-lookup"><span data-stu-id="60295-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>

<span data-ttu-id="60295-103">Obtiene un valor que indica si el sistema de seguridad en tiempo de ejecución ha concedido plena confianza al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="60295-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60295-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60295-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60295-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="60295-105">Parameters</span></span>  

 `pbFullyTrusted`  
 <span data-ttu-id="60295-106">[out] `true` Si el sistema de seguridad en tiempo de ejecución ha concedido plena confianza al ensamblado; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="60295-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60295-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="60295-107">Remarks</span></span>  

 <span data-ttu-id="60295-108">Este método devuelve un valor HRESULT de CORDBG_E_NOTREADY si la Directiva de seguridad para el ensamblado aún no se ha resuelto, es decir, si no se ha ejecutado todavía ningún código en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="60295-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60295-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60295-109">Requirements</span></span>  

 <span data-ttu-id="60295-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60295-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60295-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60295-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60295-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60295-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60295-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60295-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
