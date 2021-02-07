---
description: 'Más información acerca de: ICorDebugCode:: GetILToNativeMapping (método)'
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
ms.openlocfilehash: 808ed450fced8afecc2b637a3b990a894897b350
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711198"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="9a9c2-103">ICorDebugCode::GetILToNativeMapping (Método)</span><span class="sxs-lookup"><span data-stu-id="9a9c2-103">ICorDebugCode::GetILToNativeMapping Method</span></span>

<span data-ttu-id="9a9c2-104">Obtiene una matriz de instancias "COR_DEBUG_IL_TO_NATIVE_MAP" que representan las asignaciones de los desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="9a9c2-104">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a9c2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a9c2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a9c2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a9c2-106">Parameters</span></span>  

 `cMap`  
 <span data-ttu-id="9a9c2-107">[in] Tamaño de la matriz `map`.</span><span class="sxs-lookup"><span data-stu-id="9a9c2-107">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="9a9c2-108">enuncia Puntero al número real de elementos devueltos en la `map` matriz.</span><span class="sxs-lookup"><span data-stu-id="9a9c2-108">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="9a9c2-109">enuncia Una matriz de `COR_DEBUG_IL_TO_NATIVE_MAP` estructuras, cada una de las cuales representa una asignación de un desplazamiento de MSIL a un desplazamiento nativo.</span><span class="sxs-lookup"><span data-stu-id="9a9c2-109">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="9a9c2-110">No hay ningún orden en la matriz de elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="9a9c2-110">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a9c2-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9a9c2-111">Remarks</span></span>  

 <span data-ttu-id="9a9c2-112">El `GetILToNativeMapping` método devuelve resultados significativos solo si esta instancia de "ICorDebugCode" representa código nativo que se compiló Just-in-Time (JIT) a partir del código MSIL.</span><span class="sxs-lookup"><span data-stu-id="9a9c2-112">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a9c2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a9c2-113">Requirements</span></span>  

 <span data-ttu-id="9a9c2-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a9c2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a9c2-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a9c2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a9c2-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a9c2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a9c2-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a9c2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a9c2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a9c2-118">See also</span></span>

- [<span data-ttu-id="9a9c2-119">Interfaz ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="9a9c2-119">ICorDebugCode Interface</span></span>](icordebugcode-interface1.md)
