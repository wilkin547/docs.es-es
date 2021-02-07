---
description: 'Más información sobre: Icordebugassembly2 (:: Isfullytrusted ((método)'
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
ms.openlocfilehash: bc1c4d9a4fa84bac3469aafe8aaa061473e50413
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754113"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="d7eee-103">ICorDebugAssembly2::IsFullyTrusted (Método)</span><span class="sxs-lookup"><span data-stu-id="d7eee-103">ICorDebugAssembly2::IsFullyTrusted Method</span></span>

<span data-ttu-id="d7eee-104">Obtiene un valor que indica si el sistema de seguridad en tiempo de ejecución ha concedido plena confianza al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d7eee-104">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7eee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7eee-105">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7eee-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d7eee-106">Parameters</span></span>  

 `pbFullyTrusted`  
 <span data-ttu-id="d7eee-107">[out] `true` Si el sistema de seguridad en tiempo de ejecución ha concedido plena confianza al ensamblado; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="d7eee-107">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7eee-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d7eee-108">Remarks</span></span>  

 <span data-ttu-id="d7eee-109">Este método devuelve un valor HRESULT de CORDBG_E_NOTREADY si la Directiva de seguridad para el ensamblado aún no se ha resuelto, es decir, si no se ha ejecutado todavía ningún código en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d7eee-109">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7eee-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7eee-110">Requirements</span></span>  

 <span data-ttu-id="d7eee-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7eee-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7eee-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7eee-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7eee-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7eee-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7eee-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7eee-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
