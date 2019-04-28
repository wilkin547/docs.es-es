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
ms.openlocfilehash: fa9576f568ef1f6da3eef812abb9674aa0d81dfb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996169"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="c6207-102">ICorDebugAppDomain::IsAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="c6207-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="c6207-103">Obtiene un valor que indica si el depurador está asociado al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c6207-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6207-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6207-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6207-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6207-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="c6207-106">[out] `true` si el depurador está asociado al dominio de aplicación; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c6207-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6207-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c6207-107">Remarks</span></span>  
 <span data-ttu-id="c6207-108">No se puede usar los métodos ICorDebugController hasta que el depurador se asocia al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c6207-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6207-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6207-109">Requirements</span></span>  
 <span data-ttu-id="c6207-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6207-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6207-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6207-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6207-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6207-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6207-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6207-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
