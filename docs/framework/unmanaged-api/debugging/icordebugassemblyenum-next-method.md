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
ms.openlocfilehash: dd915a82551f5bed688a28ab77f5d6cf4e38af0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719260"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="88a4b-102">ICorDebugAssemblyEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="88a4b-102">ICorDebugAssemblyEnum::Next Method</span></span>

<span data-ttu-id="88a4b-103">Obtiene el número especificado de ensamblados de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="88a4b-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88a4b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88a4b-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88a4b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88a4b-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="88a4b-106">de Número de ensamblados que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="88a4b-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="88a4b-107">enuncia Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugAssembly que representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="88a4b-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="88a4b-108">enuncia Puntero al número de ensamblados devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="88a4b-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="88a4b-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="88a4b-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88a4b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88a4b-110">Requirements</span></span>  

 <span data-ttu-id="88a4b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88a4b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88a4b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88a4b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88a4b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88a4b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88a4b-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88a4b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
