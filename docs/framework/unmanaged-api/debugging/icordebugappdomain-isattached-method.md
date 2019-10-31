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
ms.openlocfilehash: 30e0b0c4ed9bac4abd1dc185031e41c1e3ed014a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134676"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="a8e18-102">ICorDebugAppDomain::IsAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="a8e18-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="a8e18-103">Obtiene un valor que indica si el depurador está asociado al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8e18-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8e18-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8e18-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8e18-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8e18-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="a8e18-106">[out] `true` si el depurador está asociado al dominio de aplicación; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a8e18-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8e18-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8e18-107">Remarks</span></span>  
 <span data-ttu-id="a8e18-108">Los métodos ICorDebugController no se pueden usar hasta que el depurador se asocie al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8e18-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8e18-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8e18-109">Requirements</span></span>  
 <span data-ttu-id="a8e18-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8e18-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8e18-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8e18-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8e18-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8e18-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8e18-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8e18-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
