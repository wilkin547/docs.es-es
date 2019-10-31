---
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
ms.openlocfilehash: e419ebb6ffd404368baf32e591e08c4a70645127
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121121"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="835f2-102">ICorDebugCode2::GetCodeChunks (Método)</span><span class="sxs-lookup"><span data-stu-id="835f2-102">ICorDebugCode2::GetCodeChunks Method</span></span>

<span data-ttu-id="835f2-103">Obtiene los fragmentos de código de los que está compuesto este objeto de código.</span><span class="sxs-lookup"><span data-stu-id="835f2-103">Gets the chunks of code that this code object is composed of.</span></span>

## <a name="syntax"></a><span data-ttu-id="835f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="835f2-104">Syntax</span></span>

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a><span data-ttu-id="835f2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="835f2-105">Parameters</span></span>

`cbufSize`  
<span data-ttu-id="835f2-106">de Tamaño de la matriz de `chunks`.</span><span class="sxs-lookup"><span data-stu-id="835f2-106">[in] Size of the `chunks` array.</span></span>

`pcnumChunks`  
<span data-ttu-id="835f2-107">enuncia El número de fragmentos devueltos en la matriz de `chunks`.</span><span class="sxs-lookup"><span data-stu-id="835f2-107">[out] The number of chunks returned in the `chunks` array.</span></span>

`chunks`  
<span data-ttu-id="835f2-108">enuncia Una matriz de estructuras "CodeChunkInfo (", cada una de las cuales representa un único fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="835f2-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="835f2-109">Si el valor de `cbufSize` es 0, este parámetro puede ser null.</span><span class="sxs-lookup"><span data-stu-id="835f2-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>

## <a name="remarks"></a><span data-ttu-id="835f2-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="835f2-110">Remarks</span></span>

<span data-ttu-id="835f2-111">Los fragmentos de código nunca se superpondrán y seguirán el orden en el que se habrían concatenado mediante [ICorDebugCode:: getCode](icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="835f2-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="835f2-112">Un objeto de código de lenguaje intermedio de Microsoft (MSIL) de la .NET Framework versión 2,0 incluirá un único fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="835f2-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>

## <a name="requirements"></a><span data-ttu-id="835f2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="835f2-113">Requirements</span></span>

<span data-ttu-id="835f2-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="835f2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="835f2-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="835f2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="835f2-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="835f2-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="835f2-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="835f2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
