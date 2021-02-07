---
description: 'Más información sobre: ICorDebugChainEnum (:: Next (método)'
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
ms.openlocfilehash: 5ab6665eb5af6d9f145f9aab67aeb75b4769e7e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711575"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="7b10e-103">ICorDebugChainEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="7b10e-103">ICorDebugChainEnum::Next Method</span></span>

<span data-ttu-id="7b10e-104">Obtiene el número especificado de instancias de ICorDebugChain de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="7b10e-104">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b10e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b10e-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b10e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b10e-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="7b10e-107">de El número de `ICorDebugChain` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="7b10e-107">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="7b10e-108">enuncia Matriz de punteros, cada uno de los cuales apunta a un `ICorDebugChain` objeto que representa una cadena.</span><span class="sxs-lookup"><span data-stu-id="7b10e-108">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7b10e-109">enuncia Puntero al número de `ICorDebugChain` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="7b10e-109">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="7b10e-110">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="7b10e-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b10e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b10e-111">Requirements</span></span>  

 <span data-ttu-id="7b10e-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b10e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b10e-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b10e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b10e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b10e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b10e-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b10e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
