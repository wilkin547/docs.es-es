---
title: ICorDebugModule::IsInMemory (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ae5c16f9f508511e4a15b2eae2c28d68238f1d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415898"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="58b1b-102">ICorDebugModule::IsInMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="58b1b-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="58b1b-103">Obtiene un valor que indica si este módulo sólo existe en memoria.</span><span class="sxs-lookup"><span data-stu-id="58b1b-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b1b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58b1b-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58b1b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58b1b-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="58b1b-106">[out] `true` si este módulo sólo existe en memoria; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="58b1b-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58b1b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58b1b-107">Remarks</span></span>  
 <span data-ttu-id="58b1b-108">Common language runtime (CLR) admite la carga de módulos de secuencias de bytes sin formato.</span><span class="sxs-lookup"><span data-stu-id="58b1b-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="58b1b-109">Estos módulos se denominan *módulos en memoria* y no existe en el disco.</span><span class="sxs-lookup"><span data-stu-id="58b1b-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58b1b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58b1b-110">Requirements</span></span>  
 <span data-ttu-id="58b1b-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58b1b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58b1b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58b1b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58b1b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58b1b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58b1b-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58b1b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b1b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="58b1b-115">See Also</span></span>  
    
 
