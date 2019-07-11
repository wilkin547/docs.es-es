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
ms.openlocfilehash: 7c9e2bb9ef97326c3d11553b6cabd0de0fd6e495
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747505"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="806b9-102">ICorDebugCode::GetILToNativeMapping (Método)</span><span class="sxs-lookup"><span data-stu-id="806b9-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="806b9-103">Obtiene una matriz de instancias de "COR_DEBUG_IL_TO_NATIVE_MAP" que representan las asignaciones de desplazamientos del lenguaje intermedio (MSIL) de Microsoft a los desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="806b9-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="806b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="806b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="806b9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="806b9-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="806b9-106">[in] Tamaño de la matriz `map`.</span><span class="sxs-lookup"><span data-stu-id="806b9-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="806b9-107">[out] Un puntero al número real de elementos devueltos en la `map` matriz.</span><span class="sxs-lookup"><span data-stu-id="806b9-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="806b9-108">[out] Una matriz de `COR_DEBUG_IL_TO_NATIVE_MAP` estructuras, cada uno de los cuales representa una asignación de un desplazamiento de MSIL a un desplazamiento nativo.</span><span class="sxs-lookup"><span data-stu-id="806b9-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="806b9-109">No hay ningún orden a la matriz de elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="806b9-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="806b9-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="806b9-110">Remarks</span></span>  
 <span data-ttu-id="806b9-111">El `GetILToNativeMapping` método devuelve resultados significativos solo si esta instancia de "ICorDebugCode" representa el código nativo compilado a partir de código MSIL just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="806b9-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="806b9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="806b9-112">Requirements</span></span>  
 <span data-ttu-id="806b9-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="806b9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="806b9-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="806b9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="806b9-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="806b9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="806b9-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="806b9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="806b9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="806b9-117">See also</span></span>

- [<span data-ttu-id="806b9-118">ICorDebugCode (interfaz)</span><span class="sxs-lookup"><span data-stu-id="806b9-118">ICorDebugCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
