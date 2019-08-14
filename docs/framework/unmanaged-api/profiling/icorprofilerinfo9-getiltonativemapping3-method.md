---
title: ICorProfilerInfo9::GetILToNativeMapping3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetILToNativeMapping3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 46ceef43806fda9956797935c5eeec61f865dc6e
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973795"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a><span data-ttu-id="605f6-102">ICorProfilerInfo9:: GetILToNativeMapping3 (método)</span><span class="sxs-lookup"><span data-stu-id="605f6-102">ICorProfilerInfo9::GetILToNativeMapping3 Method</span></span>
  
 <span data-ttu-id="605f6-103">Dada la dirección de inicio del código nativo, devuelve la información de asignación nativa a IL para esta versión JIT del código.</span><span class="sxs-lookup"><span data-stu-id="605f6-103">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="605f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="605f6-104">Syntax</span></span>  
  
```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```  
  
#### <a name="parameters"></a><span data-ttu-id="605f6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="605f6-105">Parameters</span></span>  
 `pNativeCodeStartAddress` \
 <span data-ttu-id="605f6-106">de Puntero al inicio de una función nativa.</span><span class="sxs-lookup"><span data-stu-id="605f6-106">[in] A pointer to the start of a native function.</span></span>

 `cMap` \
 <span data-ttu-id="605f6-107">[in] Tamaño máximo de la matriz `map`.</span><span class="sxs-lookup"><span data-stu-id="605f6-107">[in] The maximum size of the `map` array.</span></span> 

 `pcMap` \
 <span data-ttu-id="605f6-108">enuncia Número total de estructuras COR_DEBUG_IL_TO_NATIVE_MAP disponibles.</span><span class="sxs-lookup"><span data-stu-id="605f6-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>

 `map` \
 <span data-ttu-id="605f6-109">enuncia Una matriz de estructuras [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) , cada una de las cuales especifica los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="605f6-109">[out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span></span> <span data-ttu-id="605f6-110">Después de que el método `GetILToNativeMapping3` vuelva, `map` contendrá algunas o todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="605f6-110">After the `GetILToNativeMapping3` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>

## <a name="remarks"></a><span data-ttu-id="605f6-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="605f6-111">Remarks</span></span>  
 <span data-ttu-id="605f6-112">Cuando la compilación en capas está habilitada, un método puede tener más de un cuerpo de código nativo.</span><span class="sxs-lookup"><span data-stu-id="605f6-112">When tiered compilation is enabled, a method may have more than one native code body.</span></span> <span data-ttu-id="605f6-113">[ICorProfilerInfo9:: GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) devolverá las direcciones de inicio para todos los cuerpos de código nativo.</span><span class="sxs-lookup"><span data-stu-id="605f6-113">[ICorProfilerInfo9::GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span></span>

## <a name="requirements"></a><span data-ttu-id="605f6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="605f6-114">Requirements</span></span>  
 <span data-ttu-id="605f6-115">**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="605f6-115">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="605f6-116">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="605f6-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="605f6-117">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="605f6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="605f6-118">**Versiones de .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="605f6-118">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="605f6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="605f6-119">See also</span></span>
- [<span data-ttu-id="605f6-120">Interfaz ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="605f6-120">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

