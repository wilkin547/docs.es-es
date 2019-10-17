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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d64773aa0d35f2e97232576d145dfcba624812ec
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395530"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="eac78-102">ICorDebugCode2::GetCodeChunks (Método)</span><span class="sxs-lookup"><span data-stu-id="eac78-102">ICorDebugCode2::GetCodeChunks Method</span></span>

<span data-ttu-id="eac78-103">Obtiene los fragmentos de código de los que está compuesto este objeto de código.</span><span class="sxs-lookup"><span data-stu-id="eac78-103">Gets the chunks of code that this code object is composed of.</span></span>

## <a name="syntax"></a><span data-ttu-id="eac78-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eac78-104">Syntax</span></span>

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a><span data-ttu-id="eac78-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eac78-105">Parameters</span></span>

`cbufSize`  
<span data-ttu-id="eac78-106">de Tamaño de la matriz `chunks`.</span><span class="sxs-lookup"><span data-stu-id="eac78-106">[in] Size of the `chunks` array.</span></span>

`pcnumChunks`  
<span data-ttu-id="eac78-107">enuncia El número de fragmentos devueltos en la matriz `chunks`.</span><span class="sxs-lookup"><span data-stu-id="eac78-107">[out] The number of chunks returned in the `chunks` array.</span></span>

`chunks`  
<span data-ttu-id="eac78-108">enuncia Una matriz de estructuras "CodeChunkInfo (", cada una de las cuales representa un único fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="eac78-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="eac78-109">Si el valor de `cbufSize` es 0, este parámetro puede ser null.</span><span class="sxs-lookup"><span data-stu-id="eac78-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>

## <a name="remarks"></a><span data-ttu-id="eac78-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eac78-110">Remarks</span></span>

<span data-ttu-id="eac78-111">Los fragmentos de código nunca se superpondrán y seguirán el orden en el que se habrían concatenado mediante [ICorDebugCode:: getCode](icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="eac78-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="eac78-112">Un objeto de código de lenguaje intermedio de Microsoft (MSIL) de la .NET Framework versión 2,0 incluirá un único fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="eac78-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>

## <a name="requirements"></a><span data-ttu-id="eac78-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eac78-113">Requirements</span></span>

<span data-ttu-id="eac78-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eac78-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="eac78-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eac78-115">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="eac78-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eac78-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="eac78-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eac78-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
