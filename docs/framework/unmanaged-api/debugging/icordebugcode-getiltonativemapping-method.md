---
title: ICorDebugCode::GetILToNativeMapping (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13ec60999db88b9d7191a3866fcebe8098b4edee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411391"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="bebed-102">ICorDebugCode::GetILToNativeMapping (Método)</span><span class="sxs-lookup"><span data-stu-id="bebed-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="bebed-103">Obtiene una matriz de instancias de "COR_DEBUG_IL_TO_NATIVE_MAP" que representan asignaciones de desplazamientos del lenguaje intermedio (MSIL) de Microsoft a los desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="bebed-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bebed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bebed-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bebed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bebed-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="bebed-106">[in] Tamaño de la matriz `map`.</span><span class="sxs-lookup"><span data-stu-id="bebed-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="bebed-107">[out] Un puntero al número real de elementos devueltos en la `map` matriz.</span><span class="sxs-lookup"><span data-stu-id="bebed-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="bebed-108">[out] Una matriz de `COR_DEBUG_IL_TO_NATIVE_MAP` estructuras, cada uno de los cuales representa una asignación de un desplazamiento MSIL a un desplazamiento nativo.</span><span class="sxs-lookup"><span data-stu-id="bebed-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` stuctures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="bebed-109">No hay ningún orden de la matriz de elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="bebed-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bebed-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bebed-110">Remarks</span></span>  
 <span data-ttu-id="bebed-111">El `GetILToNativeMapping` método devuelve resultados significativos solo si esta instancia de "ICorDebugCode" representa el código nativo que se compila a partir de código MSIL con el compilador just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="bebed-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bebed-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bebed-112">Requirements</span></span>  
 <span data-ttu-id="bebed-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bebed-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bebed-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bebed-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bebed-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bebed-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bebed-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bebed-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bebed-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bebed-117">See Also</span></span>  
 [<span data-ttu-id="bebed-118">ICorDebugCode (interfaz1)</span><span class="sxs-lookup"><span data-stu-id="bebed-118">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
