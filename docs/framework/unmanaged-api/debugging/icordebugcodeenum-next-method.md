---
description: 'Más información sobre: ICorDebugCodeEnum (:: Next (método)'
title: ICorDebugCodeEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
ms.openlocfilehash: 51d46718891ce3df537c675175eacc4e33b92f79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764780"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="2395f-103">ICorDebugCodeEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="2395f-103">ICorDebugCodeEnum::Next Method</span></span>

<span data-ttu-id="2395f-104">Obtiene el número especificado de instancias de "ICorDebugCode" de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="2395f-104">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>

## <a name="syntax"></a><span data-ttu-id="2395f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2395f-105">Syntax</span></span>

```cpp
HRESULT Next (
    [in] ULONG  celt,
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorDebugCode *values[],
    [out] ULONG *pceltFetched
);
```

## <a name="parameters"></a><span data-ttu-id="2395f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2395f-106">Parameters</span></span>

`celt`  
<span data-ttu-id="2395f-107">de El número de `ICorDebugCode` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="2395f-107">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>

`values`  
<span data-ttu-id="2395f-108">enuncia Matriz de punteros, cada uno de los cuales señala a un `ICorDebugCode` objeto.</span><span class="sxs-lookup"><span data-stu-id="2395f-108">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>

`pceltFetched`  
<span data-ttu-id="2395f-109">enuncia Puntero al número de `ICorDebugCode` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="2395f-109">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="2395f-110">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="2395f-110">This value may be null if `celt` is one.</span></span>

## <a name="requirements"></a><span data-ttu-id="2395f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2395f-111">Requirements</span></span>

<span data-ttu-id="2395f-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2395f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="2395f-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2395f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="2395f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2395f-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="2395f-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2395f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
