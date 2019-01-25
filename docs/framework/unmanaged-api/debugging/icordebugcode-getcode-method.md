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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d057032f2a46ef29a903ae21ab13af02f9d657f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728770"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="ac913-102">ICorDebugCode::GetCode (Método)</span><span class="sxs-lookup"><span data-stu-id="ac913-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="ac913-103">Obtiene todo el código para la función especificada, con formato de desensamblado.</span><span class="sxs-lookup"><span data-stu-id="ac913-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="ac913-104">Este método está desusado en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="ac913-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ac913-105">Use [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ac913-105">Use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac913-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac913-106">Syntax</span></span>  
  
```  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac913-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac913-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="ac913-108">[in] El desplazamiento del principio de la función.</span><span class="sxs-lookup"><span data-stu-id="ac913-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="ac913-109">[in] El desplazamiento del final de la función.</span><span class="sxs-lookup"><span data-stu-id="ac913-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="ac913-110">[in] El tamaño de la `buffer` de matriz en que se devolverá el código.</span><span class="sxs-lookup"><span data-stu-id="ac913-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="ac913-111">[out] La matriz en la que se devolverá el código.</span><span class="sxs-lookup"><span data-stu-id="ac913-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="ac913-112">[out] Devuelve el número de bytes.</span><span class="sxs-lookup"><span data-stu-id="ac913-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac913-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac913-113">Remarks</span></span>  
 <span data-ttu-id="ac913-114">Si el código la función se ha dividido en varios fragmentos, se concatenan en orden creciente de desplazamiento nativo.</span><span class="sxs-lookup"><span data-stu-id="ac913-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="ac913-115">No se comprueban los límites de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="ac913-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac913-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac913-116">Requirements</span></span>  
 <span data-ttu-id="ac913-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac913-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac913-118">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac913-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac913-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac913-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac913-120">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="ac913-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac913-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac913-121">See also</span></span>
- [<span data-ttu-id="ac913-122">GetCodeChunks (método)</span><span class="sxs-lookup"><span data-stu-id="ac913-122">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)

