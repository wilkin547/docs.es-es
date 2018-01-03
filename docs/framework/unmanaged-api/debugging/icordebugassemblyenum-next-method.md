---
title: "ICorDebugAssemblyEnum::Next (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssemblyEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69f43a24caff7e67f307bbf4521094e8ebfd98cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="1c8da-102">ICorDebugAssemblyEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="1c8da-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="1c8da-103">Obtiene el número especificado de ensamblados de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="1c8da-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c8da-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c8da-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c8da-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c8da-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="1c8da-106">[in] El número de ensamblados que van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="1c8da-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="1c8da-107">[out] Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugAssembly que representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1c8da-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="1c8da-108">[out] Un puntero al número de ensamblados devueltos en realidad.</span><span class="sxs-lookup"><span data-stu-id="1c8da-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="1c8da-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="1c8da-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c8da-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c8da-110">Requirements</span></span>  
 <span data-ttu-id="1c8da-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c8da-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c8da-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c8da-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c8da-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c8da-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c8da-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c8da-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
