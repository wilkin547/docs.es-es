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
ms.openlocfilehash: 58f7964faee19f85c83d1b9b1c3e176354ae9588
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="de5fb-102">ICorDebugModule::IsInMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="de5fb-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="de5fb-103">Obtiene un valor que indica si este módulo sólo existe en memoria.</span><span class="sxs-lookup"><span data-stu-id="de5fb-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de5fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de5fb-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de5fb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de5fb-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="de5fb-106">[out] `true` si este módulo sólo existe en memoria; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="de5fb-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de5fb-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de5fb-107">Remarks</span></span>  
 <span data-ttu-id="de5fb-108">Common language runtime (CLR) admite la carga de módulos de secuencias de bytes sin formato.</span><span class="sxs-lookup"><span data-stu-id="de5fb-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="de5fb-109">Estos módulos se denominan *módulos en memoria* y no existe en el disco.</span><span class="sxs-lookup"><span data-stu-id="de5fb-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de5fb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de5fb-110">Requirements</span></span>  
 <span data-ttu-id="de5fb-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de5fb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de5fb-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de5fb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de5fb-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de5fb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de5fb-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de5fb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de5fb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="de5fb-115">See Also</span></span>  
    
 
