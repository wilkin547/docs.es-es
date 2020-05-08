---
title: ICorDebugChainEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
ms.openlocfilehash: 2d075820df534e08bdf4c2b75d36f6a60f979662
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894095"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="c0996-102">ICorDebugChainEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="c0996-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="c0996-103">Obtiene el número especificado de instancias de ICorDebugChain de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="c0996-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0996-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0996-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0996-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0996-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c0996-106">de El número de `ICorDebugChain` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="c0996-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="c0996-107">enuncia Matriz de punteros, cada uno de los cuales apunta a `ICorDebugChain` un objeto que representa una cadena.</span><span class="sxs-lookup"><span data-stu-id="c0996-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c0996-108">enuncia Puntero al número de `ICorDebugChain` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="c0996-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="c0996-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="c0996-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0996-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0996-110">Requirements</span></span>  
 <span data-ttu-id="c0996-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0996-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0996-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0996-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0996-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0996-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0996-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0996-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
