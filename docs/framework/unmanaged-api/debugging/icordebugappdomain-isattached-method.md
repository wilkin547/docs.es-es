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
ms.openlocfilehash: f0412089fee27e556c2f9230e9b34de3391b9bd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402566"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="0be76-102">ICorDebugAppDomain::IsAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="0be76-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="0be76-103">Obtiene un valor que indica si el depurador se adjunta al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0be76-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0be76-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0be76-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0be76-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0be76-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="0be76-106">[out] `true` si el depurador está conectado al dominio de aplicación; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0be76-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0be76-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0be76-107">Remarks</span></span>  
 <span data-ttu-id="0be76-108">No se puede usar los métodos ICorDebugController hasta que el depurador se asocie al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0be76-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0be76-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0be76-109">Requirements</span></span>  
 <span data-ttu-id="0be76-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0be76-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0be76-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0be76-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0be76-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0be76-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0be76-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0be76-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
