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
ms.openlocfilehash: 98709c0ce7469db1d0365d71e10d2d021cd3b3f0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777890"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="4ba93-102">ICorDebugCode::GetILToNativeMapping (Método)</span><span class="sxs-lookup"><span data-stu-id="4ba93-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="4ba93-103">Obtiene una matriz de instancias "COR_DEBUG_IL_TO_NATIVE_MAP" que representan las asignaciones de los desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="4ba93-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ba93-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ba93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ba93-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4ba93-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="4ba93-106">[in] Tamaño de la matriz `map`.</span><span class="sxs-lookup"><span data-stu-id="4ba93-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="4ba93-107">enuncia Puntero al número real de elementos devueltos en la matriz de `map`.</span><span class="sxs-lookup"><span data-stu-id="4ba93-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="4ba93-108">enuncia Matriz de estructuras de `COR_DEBUG_IL_TO_NATIVE_MAP`, cada una de las cuales representa una asignación de un desplazamiento de MSIL a un desplazamiento nativo.</span><span class="sxs-lookup"><span data-stu-id="4ba93-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="4ba93-109">No hay ningún orden en la matriz de elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="4ba93-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ba93-110">Notas</span><span class="sxs-lookup"><span data-stu-id="4ba93-110">Remarks</span></span>  
 <span data-ttu-id="4ba93-111">El método `GetILToNativeMapping` devuelve resultados significativos solo si esta instancia de "ICorDebugCode" representa código nativo que se compiló Just-in-Time (JIT) a partir del código MSIL.</span><span class="sxs-lookup"><span data-stu-id="4ba93-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ba93-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4ba93-112">Requirements</span></span>  
 <span data-ttu-id="4ba93-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ba93-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ba93-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ba93-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ba93-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ba93-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ba93-116">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ba93-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ba93-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ba93-117">See also</span></span>

- [<span data-ttu-id="4ba93-118">ICorDebugCode (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4ba93-118">ICorDebugCode Interface</span></span>](icordebugcode-interface1.md)
