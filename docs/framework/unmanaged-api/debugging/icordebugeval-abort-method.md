---
title: "ICorDebugEval::Abort (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.Abort
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a53597067d14c5b3dc1f8829b8ea0a0df07de25a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="6bcab-102">ICorDebugEval::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="6bcab-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="6bcab-103">Anula el cálculo que está realizando este objeto ICorDebugEval.</span><span class="sxs-lookup"><span data-stu-id="6bcab-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bcab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6bcab-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6bcab-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6bcab-105">Remarks</span></span>  
 <span data-ttu-id="6bcab-106">Si se anida la evaluación y no es el más reciente, la `Abort` método puede producir un error.</span><span class="sxs-lookup"><span data-stu-id="6bcab-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bcab-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6bcab-107">Requirements</span></span>  
 <span data-ttu-id="6bcab-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bcab-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bcab-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6bcab-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6bcab-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bcab-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bcab-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bcab-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
