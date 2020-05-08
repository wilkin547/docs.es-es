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
ms.openlocfilehash: 155354b335caf83c466c8d9d6711f36c7efc9298
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894807"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="b2041-102">ICorDebugAssemblyEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="b2041-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="b2041-103">Obtiene el número especificado de ensamblados de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="b2041-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2041-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2041-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2041-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2041-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b2041-106">de Número de ensamblados que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="b2041-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="b2041-107">enuncia Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugAssembly que representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b2041-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b2041-108">enuncia Puntero al número de ensamblados devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="b2041-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="b2041-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="b2041-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2041-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2041-110">Requirements</span></span>  
 <span data-ttu-id="b2041-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2041-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2041-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2041-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2041-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2041-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2041-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2041-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
