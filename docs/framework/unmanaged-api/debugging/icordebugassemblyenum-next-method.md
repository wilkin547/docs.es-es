---
title: ICorDebugAssemblyEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00adc852a0940766cdd4188ffa5d6be2b472e51f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744878"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="fe003-102">ICorDebugAssemblyEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="fe003-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="fe003-103">Obtiene el número especificado de los ensamblados de la colección, empezando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="fe003-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe003-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe003-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe003-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe003-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="fe003-106">[in] El número de ensamblados que van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="fe003-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="fe003-107">[out] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugAssembly que representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fe003-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="fe003-108">[out] Un puntero al número de ensamblados devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="fe003-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="fe003-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="fe003-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe003-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe003-110">Requirements</span></span>  
 <span data-ttu-id="fe003-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe003-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe003-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe003-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe003-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe003-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe003-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe003-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
