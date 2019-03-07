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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd3b977a894f8cb1fc9a866f5a43265d917db513
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494446"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="1c4df-102">ICorDebugAssembly2::IsFullyTrusted (Método)</span><span class="sxs-lookup"><span data-stu-id="1c4df-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="1c4df-103">Obtiene un valor que indica si el ensamblado se ha concedido confianza completa por el sistema de seguridad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c4df-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c4df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c4df-104">Syntax</span></span>  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c4df-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c4df-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="1c4df-106">[out] `true` si se ha concedido al ensamblado plena confianza por el sistema de seguridad en tiempo de ejecución; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1c4df-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c4df-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c4df-107">Remarks</span></span>  
 <span data-ttu-id="1c4df-108">Este método devuelve un HRESULT de CORDBG_E_NOTREADY si la directiva de seguridad para el ensamblado aún no se ha resuelta, es decir, si no hay código en el ensamblado se ha ejecutado todavía.</span><span class="sxs-lookup"><span data-stu-id="1c4df-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c4df-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c4df-109">Requirements</span></span>  
 <span data-ttu-id="1c4df-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c4df-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c4df-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c4df-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c4df-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c4df-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c4df-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c4df-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
