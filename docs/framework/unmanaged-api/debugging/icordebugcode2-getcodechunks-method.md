---
description: 'Más información sobre: ICorDebugCode2:: Getcodechunks ((método)'
title: ICorDebugCode2::GetCodeChunks (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
ms.openlocfilehash: 371d077466ff2390293d9d4e320d4c95a992fe54
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764975"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="ed7b8-103">ICorDebugCode2::GetCodeChunks (Método)</span><span class="sxs-lookup"><span data-stu-id="ed7b8-103">ICorDebugCode2::GetCodeChunks Method</span></span>

<span data-ttu-id="ed7b8-104">Obtiene los fragmentos de código de los que está compuesto este objeto de código.</span><span class="sxs-lookup"><span data-stu-id="ed7b8-104">Gets the chunks of code that this code object is composed of.</span></span>

## <a name="syntax"></a><span data-ttu-id="ed7b8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed7b8-105">Syntax</span></span>

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a><span data-ttu-id="ed7b8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed7b8-106">Parameters</span></span>

`cbufSize`  
<span data-ttu-id="ed7b8-107">de Tamaño de la `chunks` matriz.</span><span class="sxs-lookup"><span data-stu-id="ed7b8-107">[in] Size of the `chunks` array.</span></span>

`pcnumChunks`  
<span data-ttu-id="ed7b8-108">enuncia El número de fragmentos devueltos en la `chunks` matriz.</span><span class="sxs-lookup"><span data-stu-id="ed7b8-108">[out] The number of chunks returned in the `chunks` array.</span></span>

`chunks`  
<span data-ttu-id="ed7b8-109">enuncia Una matriz de estructuras "CodeChunkInfo (", cada una de las cuales representa un único fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="ed7b8-109">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="ed7b8-110">Si el valor de `cbufSize` es 0, este parámetro puede ser null.</span><span class="sxs-lookup"><span data-stu-id="ed7b8-110">If the value of `cbufSize` is 0, this parameter can be null.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed7b8-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ed7b8-111">Remarks</span></span>

<span data-ttu-id="ed7b8-112">Los fragmentos de código nunca se superpondrán y seguirán el orden en el que se habrían concatenado mediante [ICorDebugCode:: getCode](icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="ed7b8-112">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="ed7b8-113">Un objeto de código de lenguaje intermedio de Microsoft (MSIL) de la .NET Framework versión 2,0 incluirá un único fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="ed7b8-113">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>

## <a name="requirements"></a><span data-ttu-id="ed7b8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed7b8-114">Requirements</span></span>

<span data-ttu-id="ed7b8-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed7b8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ed7b8-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed7b8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="ed7b8-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed7b8-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="ed7b8-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed7b8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
