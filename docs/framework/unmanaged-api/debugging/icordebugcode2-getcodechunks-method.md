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
ms.openlocfilehash: 4bbc7ac7d87c6a5d36dc3432c603bb7d16d62c00
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747424"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="7caa2-102">ICorDebugCode2::GetCodeChunks (Método)</span><span class="sxs-lookup"><span data-stu-id="7caa2-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="7caa2-103">Obtiene los fragmentos de código de los que está compuesto este objeto de código.</span><span class="sxs-lookup"><span data-stu-id="7caa2-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7caa2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7caa2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7caa2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7caa2-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="7caa2-106">[in] Tamaño de la `chunks` matriz.</span><span class="sxs-lookup"><span data-stu-id="7caa2-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="7caa2-107">[out] El número de fragmentos que se devuelven en el `chunks` matriz.</span><span class="sxs-lookup"><span data-stu-id="7caa2-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="7caa2-108">[out] Una matriz de estructuras "CodeChunkInfo", cada uno de los cuales representa un único fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="7caa2-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="7caa2-109">Si el valor de `cbufSize` es 0, este parámetro puede ser null.</span><span class="sxs-lookup"><span data-stu-id="7caa2-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7caa2-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7caa2-110">Remarks</span></span>  
 <span data-ttu-id="7caa2-111">Los fragmentos de código nunca se superpondrán y siguen el orden en que habría concatenados [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="7caa2-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="7caa2-112">Un objeto de código de lenguaje intermedio (MSIL) de Microsoft en la versión 2.0 de .NET Framework, perderá un único fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="7caa2-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7caa2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7caa2-113">Requirements</span></span>  
 <span data-ttu-id="7caa2-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7caa2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7caa2-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7caa2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7caa2-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7caa2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7caa2-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7caa2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7caa2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7caa2-118">See also</span></span>
