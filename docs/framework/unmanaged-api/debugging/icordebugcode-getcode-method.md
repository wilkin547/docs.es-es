---
title: ICorDebugCode::GetCode (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
ms.openlocfilehash: 59a497d203d241bbc6e0f884007d4a401c112073
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893655"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="174a0-102">ICorDebugCode::GetCode (Método)</span><span class="sxs-lookup"><span data-stu-id="174a0-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="174a0-103">Obtiene todo el código para la función especificada, con formato de desensamblado.</span><span class="sxs-lookup"><span data-stu-id="174a0-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="174a0-104">Este método está en desuso en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="174a0-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="174a0-105">Use [ICorDebugCode2:: getcodechunks (](icordebugcode2-getcodechunks-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="174a0-105">Use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="174a0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="174a0-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="174a0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="174a0-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="174a0-108">de Desplazamiento del principio de la función.</span><span class="sxs-lookup"><span data-stu-id="174a0-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="174a0-109">de Desplazamiento del final de la función.</span><span class="sxs-lookup"><span data-stu-id="174a0-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="174a0-110">de Tamaño de la `buffer` matriz en la que se devolverá el código.</span><span class="sxs-lookup"><span data-stu-id="174a0-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="174a0-111">enuncia Matriz en la que se devolverá el código.</span><span class="sxs-lookup"><span data-stu-id="174a0-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="174a0-112">enuncia Número de bytes devueltos.</span><span class="sxs-lookup"><span data-stu-id="174a0-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="174a0-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="174a0-113">Remarks</span></span>  
 <span data-ttu-id="174a0-114">Si el código de la función se ha dividido en varios fragmentos, se concatenan en orden de desplazamiento nativo creciente.</span><span class="sxs-lookup"><span data-stu-id="174a0-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="174a0-115">Los límites de la instrucción no se comprueban.</span><span class="sxs-lookup"><span data-stu-id="174a0-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="174a0-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="174a0-116">Requirements</span></span>  
 <span data-ttu-id="174a0-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="174a0-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="174a0-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="174a0-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="174a0-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="174a0-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="174a0-120">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="174a0-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="174a0-121">Consulta también</span><span class="sxs-lookup"><span data-stu-id="174a0-121">See also</span></span>

- [<span data-ttu-id="174a0-122">Método GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="174a0-122">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
