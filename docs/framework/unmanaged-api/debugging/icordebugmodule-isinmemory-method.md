---
title: "ICorDebugModule::IsInMemory (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.IsInMemory
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 448458874c4de96503261bc0fe34fae160395c49
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="90a06-102">ICorDebugModule::IsInMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="90a06-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="90a06-103">Obtiene un valor que indica si este módulo sólo existe en memoria.</span><span class="sxs-lookup"><span data-stu-id="90a06-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90a06-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90a06-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90a06-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="90a06-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="90a06-106">[out] `true` si este módulo sólo existe en memoria; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="90a06-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90a06-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="90a06-107">Remarks</span></span>  
 <span data-ttu-id="90a06-108">Common language runtime (CLR) admite la carga de módulos de secuencias de bytes sin formato.</span><span class="sxs-lookup"><span data-stu-id="90a06-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="90a06-109">Estos módulos se denominan *módulos en memoria* y no existe en el disco.</span><span class="sxs-lookup"><span data-stu-id="90a06-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90a06-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90a06-110">Requirements</span></span>  
 <span data-ttu-id="90a06-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90a06-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90a06-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90a06-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90a06-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90a06-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90a06-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90a06-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a06-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="90a06-115">See Also</span></span>  
    
 
