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
ms.openlocfilehash: 3de85626be6ae8e4769ac261f4de1479461417ec
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893541"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="838bc-102">ICorDebugCode::GetILToNativeMapping (Método)</span><span class="sxs-lookup"><span data-stu-id="838bc-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="838bc-103">Obtiene una matriz de instancias "COR_DEBUG_IL_TO_NATIVE_MAP" que representan las asignaciones de los desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="838bc-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="838bc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="838bc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="838bc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="838bc-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="838bc-106">[in] Tamaño de la matriz `map`.</span><span class="sxs-lookup"><span data-stu-id="838bc-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="838bc-107">enuncia Puntero al número real de elementos devueltos en la `map` matriz.</span><span class="sxs-lookup"><span data-stu-id="838bc-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="838bc-108">enuncia Una matriz de `COR_DEBUG_IL_TO_NATIVE_MAP` estructuras, cada una de las cuales representa una asignación de un desplazamiento de MSIL a un desplazamiento nativo.</span><span class="sxs-lookup"><span data-stu-id="838bc-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="838bc-109">No hay ningún orden en la matriz de elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="838bc-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="838bc-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="838bc-110">Remarks</span></span>  
 <span data-ttu-id="838bc-111">El `GetILToNativeMapping` método devuelve resultados significativos solo si esta instancia de "ICorDebugCode" representa código nativo que se compiló Just-in-Time (JIT) a partir del código MSIL.</span><span class="sxs-lookup"><span data-stu-id="838bc-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="838bc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="838bc-112">Requirements</span></span>  
 <span data-ttu-id="838bc-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="838bc-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="838bc-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="838bc-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="838bc-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="838bc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="838bc-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="838bc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="838bc-117">Consulta también</span><span class="sxs-lookup"><span data-stu-id="838bc-117">See also</span></span>

- [<span data-ttu-id="838bc-118">Interfaz ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="838bc-118">ICorDebugCode Interface</span></span>](icordebugcode-interface1.md)
