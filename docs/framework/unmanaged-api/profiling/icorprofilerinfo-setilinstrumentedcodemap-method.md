---
description: 'Más información acerca de: ICorProfilerInfo:: SetILInstrumentedCodeMap ((método)'
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
ms.openlocfilehash: f9ed01b91f740a8bd95f4ad049076feb02363b8f
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760397"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="c60b2-103">ICorProfilerInfo::SetILInstrumentedCodeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="c60b2-103">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>

<span data-ttu-id="c60b2-104">Establece un mapa de código para la función especificada utilizando las entradas de asignación del lenguaje intermedio de Microsoft (MSIL) especificadas.</span><span class="sxs-lookup"><span data-stu-id="c60b2-104">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>

> [!NOTE]
> <span data-ttu-id="c60b2-105">En la .NET Framework versión 2,0, la llamada a `SetILInstrumentedCodeMap` `FunctionID` que representa una función genérica en un dominio de aplicación determinado afectará a todas las instancias de esa función en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c60b2-105">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>

## <a name="syntax"></a><span data-ttu-id="c60b2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c60b2-106">Syntax</span></span>

```cpp
HRESULT SetILInstrumentedCodeMap(
    [in]  FunctionID functionId,
    [in]  BOOL       fStartJit,
    [in]  ULONG      cILMapEntries,
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);
```

## <a name="parameters"></a><span data-ttu-id="c60b2-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c60b2-107">Parameters</span></span>

<span data-ttu-id="c60b2-108">`functionId` de IDENTIFICADOR de la función para la que se va a establecer el mapa de código.</span><span class="sxs-lookup"><span data-stu-id="c60b2-108">`functionId` [in] The ID of the function for which to set the code map.</span></span>

<span data-ttu-id="c60b2-109">`fStartJit` de Valor booleano que indica si la llamada al `SetILInstrumentedCodeMap` método es la primera para un determinado `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="c60b2-109">`fStartJit` [in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="c60b2-110">Establezca `fStartJit` en `true` en la primera llamada a `SetILInstrumentedCodeMap` para un determinado `FunctionID` y, a `false` partir de ese momento,.</span><span class="sxs-lookup"><span data-stu-id="c60b2-110">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>

<span data-ttu-id="c60b2-111">`cILMapEntries` de Número de elementos de la `cILMapEntries` matriz.</span><span class="sxs-lookup"><span data-stu-id="c60b2-111">`cILMapEntries` [in] The number of elements in the `cILMapEntries` array.</span></span>

<span data-ttu-id="c60b2-112">`rgILMapEntries` de Matriz de estructuras de COR_IL_MAP, cada una de las cuales especifica un desplazamiento de MSIL.</span><span class="sxs-lookup"><span data-stu-id="c60b2-112">`rgILMapEntries` [in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>

## <a name="remarks"></a><span data-ttu-id="c60b2-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c60b2-113">Remarks</span></span>

<span data-ttu-id="c60b2-114">A menudo, un generador de perfiles inserta instrucciones dentro del código fuente de un método para instrumentar ese método (por ejemplo, para notificar cuando se alcanza una línea de código fuente determinada).</span><span class="sxs-lookup"><span data-stu-id="c60b2-114">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="c60b2-115">`SetILInstrumentedCodeMap` permite a un generador de perfiles asignar las instrucciones de MSIL originales a sus nuevas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="c60b2-115">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="c60b2-116">Un generador de perfiles puede utilizar el método [ICorProfilerInfo:: GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) para obtener el desplazamiento de MSIL original para un desplazamiento nativo determinado.</span><span class="sxs-lookup"><span data-stu-id="c60b2-116">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>

<span data-ttu-id="c60b2-117">El depurador asumirá que cada desplazamiento anterior se refiere a un desplazamiento de MSIL en el código MSIL original, sin modificar, y que cada nuevo desplazamiento hace referencia al desplazamiento de MSIL en el nuevo código instrumentado.</span><span class="sxs-lookup"><span data-stu-id="c60b2-117">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="c60b2-118">La asignación debe ordenarse en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="c60b2-118">The map should be sorted in increasing order.</span></span> <span data-ttu-id="c60b2-119">Para que funcione correctamente, siga estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="c60b2-119">For stepping to work properly, follow these guidelines:</span></span>

- <span data-ttu-id="c60b2-120">No reordene el código MSIL instrumentado.</span><span class="sxs-lookup"><span data-stu-id="c60b2-120">Do not reorder instrumented MSIL code.</span></span>

- <span data-ttu-id="c60b2-121">No quite el código MSIL original.</span><span class="sxs-lookup"><span data-stu-id="c60b2-121">Do not remove the original MSIL code.</span></span>

- <span data-ttu-id="c60b2-122">Incluya entradas para todos los puntos de secuencia del archivo de base de datos de programa (PDB) en el mapa.</span><span class="sxs-lookup"><span data-stu-id="c60b2-122">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="c60b2-123">La asignación no interpola las entradas que faltan.</span><span class="sxs-lookup"><span data-stu-id="c60b2-123">The map does not interpolate missing entries.</span></span> <span data-ttu-id="c60b2-124">Por lo tanto, dada la siguiente asignación:</span><span class="sxs-lookup"><span data-stu-id="c60b2-124">So, given the following map:</span></span>

  <span data-ttu-id="c60b2-125">(0 Old, 0 nuevo)</span><span class="sxs-lookup"><span data-stu-id="c60b2-125">(0 old, 0 new)</span></span>

  <span data-ttu-id="c60b2-126">(5 antiguos, 10 nuevos)</span><span class="sxs-lookup"><span data-stu-id="c60b2-126">(5 old, 10 new)</span></span>

  <span data-ttu-id="c60b2-127">(9 antiguos, 20 nuevos)</span><span class="sxs-lookup"><span data-stu-id="c60b2-127">(9 old, 20 new)</span></span>

  - <span data-ttu-id="c60b2-128">Un desplazamiento anterior de 0, 1, 2, 3 o 4 se asignará al nuevo desplazamiento 0.</span><span class="sxs-lookup"><span data-stu-id="c60b2-128">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>

  - <span data-ttu-id="c60b2-129">Un desplazamiento anterior de 5, 6, 7 u 8 se asignará al nuevo desplazamiento 10.</span><span class="sxs-lookup"><span data-stu-id="c60b2-129">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>

  - <span data-ttu-id="c60b2-130">Un desplazamiento anterior de 9 o superior se asignará al nuevo desplazamiento 20.</span><span class="sxs-lookup"><span data-stu-id="c60b2-130">An old offset of 9 or higher will be mapped to new offset 20.</span></span>

  - <span data-ttu-id="c60b2-131">Un nuevo desplazamiento de 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 se asignará al desplazamiento anterior 0.</span><span class="sxs-lookup"><span data-stu-id="c60b2-131">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>

  - <span data-ttu-id="c60b2-132">Un nuevo desplazamiento de 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 se asignará al anterior desplazamiento 5.</span><span class="sxs-lookup"><span data-stu-id="c60b2-132">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>

  - <span data-ttu-id="c60b2-133">Un nuevo desplazamiento de 20 o superior se asignará al anterior desplazamiento 9.</span><span class="sxs-lookup"><span data-stu-id="c60b2-133">A new offset of 20 or higher will be mapped to old offset 9.</span></span>

<span data-ttu-id="c60b2-134">En el .NET Framework 3,5 y versiones anteriores, se asigna la `rgILMapEntries` matriz mediante una llamada al método [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) .</span><span class="sxs-lookup"><span data-stu-id="c60b2-134">In the .NET Framework 3.5 and previous versions, you allocate the `rgILMapEntries` array by calling the [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) method.</span></span> <span data-ttu-id="c60b2-135">Dado que el tiempo de ejecución toma la propiedad de esta memoria, el generador de perfiles no debe intentar liberarla.</span><span class="sxs-lookup"><span data-stu-id="c60b2-135">Because the runtime takes ownership of this memory, the profiler should not attempt to free it.</span></span>

## <a name="requirements"></a><span data-ttu-id="c60b2-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c60b2-136">Requirements</span></span>

<span data-ttu-id="c60b2-137">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c60b2-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c60b2-138">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c60b2-138">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c60b2-139">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c60b2-139">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c60b2-140">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c60b2-140">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c60b2-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c60b2-141">See also</span></span>

- [<span data-ttu-id="c60b2-142">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c60b2-142">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
