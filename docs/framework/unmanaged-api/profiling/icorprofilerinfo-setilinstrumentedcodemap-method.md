---
title: ICorProfilerInfo::SetILInstrumentedCodeMap (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type:
- apiref
ms.openlocfilehash: cac8e9570dab55af6b6e1fcf6f53b6a697727972
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502917"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="8a45a-102">ICorProfilerInfo::SetILInstrumentedCodeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="8a45a-102">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>

<span data-ttu-id="8a45a-103">Establece un mapa de código para la función especificada utilizando las entradas de asignación del lenguaje intermedio de Microsoft (MSIL) especificadas.</span><span class="sxs-lookup"><span data-stu-id="8a45a-103">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>

> [!NOTE]
> <span data-ttu-id="8a45a-104">En la .NET Framework versión 2,0, la llamada a `SetILInstrumentedCodeMap` `FunctionID` que representa una función genérica en un dominio de aplicación determinado afectará a todas las instancias de esa función en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8a45a-104">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a45a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a45a-105">Syntax</span></span>

```cpp
HRESULT SetILInstrumentedCodeMap(
    [in]  FunctionID functionId,
    [in]  BOOL       fStartJit,
    [in]  ULONG      cILMapEntries,
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);
```

## <a name="parameters"></a><span data-ttu-id="8a45a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a45a-106">Parameters</span></span>

`functionId`\
<span data-ttu-id="8a45a-107">de IDENTIFICADOR de la función para la que se va a establecer el mapa de código.</span><span class="sxs-lookup"><span data-stu-id="8a45a-107">[in] The ID of the function for which to set the code map.</span></span>

`fStartJit`\
<span data-ttu-id="8a45a-108">de Valor booleano que indica si la llamada al `SetILInstrumentedCodeMap` método es la primera para un determinado `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="8a45a-108">[in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="8a45a-109">Establezca `fStartJit` en `true` en la primera llamada a `SetILInstrumentedCodeMap` para un determinado `FunctionID` y, a `false` partir de ese momento,.</span><span class="sxs-lookup"><span data-stu-id="8a45a-109">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>

`cILMapEntries`\
<span data-ttu-id="8a45a-110">de Número de elementos de la `cILMapEntries` matriz.</span><span class="sxs-lookup"><span data-stu-id="8a45a-110">[in] The number of elements in the `cILMapEntries` array.</span></span>

`rgILMapEntries`\
<span data-ttu-id="8a45a-111">de Matriz de estructuras de COR_IL_MAP, cada una de las cuales especifica un desplazamiento de MSIL.</span><span class="sxs-lookup"><span data-stu-id="8a45a-111">[in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a45a-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a45a-112">Remarks</span></span>

<span data-ttu-id="8a45a-113">A menudo, un generador de perfiles inserta instrucciones dentro del código fuente de un método para instrumentar ese método (por ejemplo, para notificar cuando se alcanza una línea de código fuente determinada).</span><span class="sxs-lookup"><span data-stu-id="8a45a-113">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="8a45a-114">`SetILInstrumentedCodeMap`permite a un generador de perfiles asignar las instrucciones de MSIL originales a sus nuevas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="8a45a-114">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="8a45a-115">Un generador de perfiles puede utilizar el método [ICorProfilerInfo:: GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) para obtener el desplazamiento de MSIL original para un desplazamiento nativo determinado.</span><span class="sxs-lookup"><span data-stu-id="8a45a-115">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>

<span data-ttu-id="8a45a-116">El depurador asumirá que cada desplazamiento anterior se refiere a un desplazamiento de MSIL en el código MSIL original, sin modificar, y que cada nuevo desplazamiento hace referencia al desplazamiento de MSIL en el nuevo código instrumentado.</span><span class="sxs-lookup"><span data-stu-id="8a45a-116">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="8a45a-117">La asignación debe ordenarse en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="8a45a-117">The map should be sorted in increasing order.</span></span> <span data-ttu-id="8a45a-118">Para que funcione correctamente, siga estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="8a45a-118">For stepping to work properly, follow these guidelines:</span></span>

- <span data-ttu-id="8a45a-119">No reordene el código MSIL instrumentado.</span><span class="sxs-lookup"><span data-stu-id="8a45a-119">Do not reorder instrumented MSIL code.</span></span>

- <span data-ttu-id="8a45a-120">No quite el código MSIL original.</span><span class="sxs-lookup"><span data-stu-id="8a45a-120">Do not remove the original MSIL code.</span></span>

- <span data-ttu-id="8a45a-121">Incluya entradas para todos los puntos de secuencia del archivo de base de datos de programa (PDB) en el mapa.</span><span class="sxs-lookup"><span data-stu-id="8a45a-121">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="8a45a-122">La asignación no interpola las entradas que faltan.</span><span class="sxs-lookup"><span data-stu-id="8a45a-122">The map does not interpolate missing entries.</span></span> <span data-ttu-id="8a45a-123">Por lo tanto, dada la siguiente asignación:</span><span class="sxs-lookup"><span data-stu-id="8a45a-123">So, given the following map:</span></span>

  <span data-ttu-id="8a45a-124">(0 Old, 0 nuevo)</span><span class="sxs-lookup"><span data-stu-id="8a45a-124">(0 old, 0 new)</span></span>

  <span data-ttu-id="8a45a-125">(5 antiguos, 10 nuevos)</span><span class="sxs-lookup"><span data-stu-id="8a45a-125">(5 old, 10 new)</span></span>

  <span data-ttu-id="8a45a-126">(9 antiguos, 20 nuevos)</span><span class="sxs-lookup"><span data-stu-id="8a45a-126">(9 old, 20 new)</span></span>

  - <span data-ttu-id="8a45a-127">Un desplazamiento anterior de 0, 1, 2, 3 o 4 se asignará al nuevo desplazamiento 0.</span><span class="sxs-lookup"><span data-stu-id="8a45a-127">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>

  - <span data-ttu-id="8a45a-128">Un desplazamiento anterior de 5, 6, 7 u 8 se asignará al nuevo desplazamiento 10.</span><span class="sxs-lookup"><span data-stu-id="8a45a-128">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>

  - <span data-ttu-id="8a45a-129">Un desplazamiento anterior de 9 o superior se asignará al nuevo desplazamiento 20.</span><span class="sxs-lookup"><span data-stu-id="8a45a-129">An old offset of 9 or higher will be mapped to new offset 20.</span></span>

  - <span data-ttu-id="8a45a-130">Un nuevo desplazamiento de 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 se asignará al desplazamiento anterior 0.</span><span class="sxs-lookup"><span data-stu-id="8a45a-130">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>

  - <span data-ttu-id="8a45a-131">Un nuevo desplazamiento de 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 se asignará al anterior desplazamiento 5.</span><span class="sxs-lookup"><span data-stu-id="8a45a-131">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>

  - <span data-ttu-id="8a45a-132">Un nuevo desplazamiento de 20 o superior se asignará al anterior desplazamiento 9.</span><span class="sxs-lookup"><span data-stu-id="8a45a-132">A new offset of 20 or higher will be mapped to old offset 9.</span></span>

<span data-ttu-id="8a45a-133">En el .NET Framework 3,5 y versiones anteriores, se asigna la `rgILMapEntries` matriz mediante una llamada al método [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) .</span><span class="sxs-lookup"><span data-stu-id="8a45a-133">In the .NET Framework 3.5 and previous versions, you allocate the `rgILMapEntries` array by calling the [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) method.</span></span> <span data-ttu-id="8a45a-134">Dado que el tiempo de ejecución toma la propiedad de esta memoria, el generador de perfiles no debe intentar liberarla.</span><span class="sxs-lookup"><span data-stu-id="8a45a-134">Because the runtime takes ownership of this memory, the profiler should not attempt to free it.</span></span>

## <a name="requirements"></a><span data-ttu-id="8a45a-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a45a-135">Requirements</span></span>

<span data-ttu-id="8a45a-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a45a-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="8a45a-137">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a45a-137">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="8a45a-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a45a-138">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="8a45a-139">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a45a-139">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8a45a-140">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="8a45a-140">See also</span></span>

- [<span data-ttu-id="8a45a-141">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a45a-141">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
