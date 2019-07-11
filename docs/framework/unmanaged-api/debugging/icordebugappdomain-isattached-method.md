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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a3f01edcd6ce1d16ab2c651a66d2fd9cd2eb0ba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737823"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="3188e-102">ICorDebugAppDomain::IsAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="3188e-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="3188e-103">Obtiene un valor que indica si el depurador está asociado al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3188e-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3188e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3188e-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3188e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3188e-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="3188e-106">[out] `true` si el depurador está asociado al dominio de aplicación; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="3188e-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3188e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3188e-107">Remarks</span></span>  
 <span data-ttu-id="3188e-108">No se puede usar los métodos ICorDebugController hasta que el depurador se asocia al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3188e-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3188e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3188e-109">Requirements</span></span>  
 <span data-ttu-id="3188e-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3188e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3188e-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3188e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3188e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3188e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3188e-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3188e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
