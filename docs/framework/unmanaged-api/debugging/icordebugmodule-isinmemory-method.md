---
description: 'Más información acerca de: ICorDebugModule:: Isinmemory ((método)'
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
ms.openlocfilehash: 41454ede15e1d45775af8fb0ab7a6b571d9c0e41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660094"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="4f1bc-103">ICorDebugModule::IsInMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="4f1bc-103">ICorDebugModule::IsInMemory Method</span></span>

<span data-ttu-id="4f1bc-104">Obtiene un valor que indica si este módulo solo existe en la memoria.</span><span class="sxs-lookup"><span data-stu-id="4f1bc-104">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f1bc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f1bc-105">Syntax</span></span>  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f1bc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f1bc-106">Parameters</span></span>  

 `pInMemory`  
 <span data-ttu-id="4f1bc-107">[out] `true` Si este módulo solo existe en la memoria; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="4f1bc-107">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f1bc-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4f1bc-108">Remarks</span></span>  

 <span data-ttu-id="4f1bc-109">El Common Language Runtime (CLR) admite la carga de módulos desde secuencias sin formato de bytes.</span><span class="sxs-lookup"><span data-stu-id="4f1bc-109">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="4f1bc-110">Estos módulos se denominan *módulos en memoria* y no existen en el disco.</span><span class="sxs-lookup"><span data-stu-id="4f1bc-110">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f1bc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f1bc-111">Requirements</span></span>  

 <span data-ttu-id="4f1bc-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f1bc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f1bc-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f1bc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f1bc-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f1bc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f1bc-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f1bc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f1bc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f1bc-116">See also</span></span>
