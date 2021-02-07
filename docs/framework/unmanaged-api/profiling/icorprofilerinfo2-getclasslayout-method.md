---
description: 'Más información acerca de: ICorProfilerInfo2:: GetClassLayout (método)'
title: ICorProfilerInfo2::GetClassLayout (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassLayout
helpviewer_keywords:
- ICorProfilerInfo2::GetClassLayout method [.NET Framework profiling]
- GetClassLayout method, ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: a3a36987-5666-4e2f-95b5-d0cb246502ec
topic_type:
- apiref
ms.openlocfilehash: 6b515ff84240e227914404379efcfc063c25c5a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760502"
---
# <a name="icorprofilerinfo2getclasslayout-method"></a><span data-ttu-id="bc545-103">ICorProfilerInfo2::GetClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="bc545-103">ICorProfilerInfo2::GetClassLayout Method</span></span>

<span data-ttu-id="bc545-104">Obtiene información sobre la distribución, en memoria, de los campos definidos por la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="bc545-104">Gets information about the layout, in memory, of the fields defined by the specified class.</span></span> <span data-ttu-id="bc545-105">Es decir, este método obtiene los desplazamientos de los campos de la clase.</span><span class="sxs-lookup"><span data-stu-id="bc545-105">That is, this method gets the offsets of the class's fields.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc545-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc545-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout(  
    [in]  ClassID classID,  
    [in, out] COR_FIELD_OFFSET rFieldOffset[],  
    [in]  ULONG cFieldOffset,  
    [out] ULONG *pcFieldOffset,  
    [out] ULONG *pulClassSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc545-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc545-107">Parameters</span></span>  

 `classID`  
 <span data-ttu-id="bc545-108">[in] Identificador de la clase para la cual se recuperará la distribución.</span><span class="sxs-lookup"><span data-stu-id="bc545-108">[in] The ID of the class for which the layout will be retrieved.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="bc545-109">[in, out] Matriz de estructuras de [COR_FIELD_OFFSET](../metadata/cor-field-offset-structure.md) , cada una de las cuales contiene los tokens y desplazamientos de los campos de la clase.</span><span class="sxs-lookup"><span data-stu-id="bc545-109">[in, out] An array of [COR_FIELD_OFFSET](../metadata/cor-field-offset-structure.md) structures, each of which contains the tokens and offsets of the class's fields.</span></span>  
  
 `cFieldOffset`  
 <span data-ttu-id="bc545-110">[in] Tamaño de la matriz `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="bc545-110">[in] The size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="bc545-111">[out] Puntero al número total de elementos disponibles.</span><span class="sxs-lookup"><span data-stu-id="bc545-111">[out] A pointer to the total number of available elements.</span></span> <span data-ttu-id="bc545-112">Si `cFieldOffset` es 0, este valor indica el número de elementos necesario.</span><span class="sxs-lookup"><span data-stu-id="bc545-112">If `cFieldOffset` is 0, this value indicates the number of elements needed.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="bc545-113">[out] Puntero a una ubicación que contiene el tamaño, en bytes, de la clase.</span><span class="sxs-lookup"><span data-stu-id="bc545-113">[out] A pointer to a location that contains the size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc545-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bc545-114">Remarks</span></span>  

 <span data-ttu-id="bc545-115">El método `GetClassLayout` solo devuelve los campos definidos por la propia clase.</span><span class="sxs-lookup"><span data-stu-id="bc545-115">The `GetClassLayout` method returns only the fields defined by the class itself.</span></span> <span data-ttu-id="bc545-116">Si la clase primaria de la clase también tiene campos definidos, el generador de perfiles debe llamar a `GetClassLayout` en la clase primaria para obtener dichos campos.</span><span class="sxs-lookup"><span data-stu-id="bc545-116">If the class's parent class has defined fields as well, the profiler must call `GetClassLayout` on the parent class to obtain those fields.</span></span>  
  
 <span data-ttu-id="bc545-117">Si usa `GetClassLayout` con clases de cadena, el método producirá un error con el código E_INVALIDARG.</span><span class="sxs-lookup"><span data-stu-id="bc545-117">If you use `GetClassLayout` with string classes, the method will fail with error code E_INVALIDARG.</span></span> <span data-ttu-id="bc545-118">Use [ICorProfilerInfo2:: GetStringLayout (](icorprofilerinfo2-getstringlayout-method.md) para obtener información sobre el diseño de una cadena.</span><span class="sxs-lookup"><span data-stu-id="bc545-118">Use [ICorProfilerInfo2::GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) to get information about the layout of a string.</span></span> <span data-ttu-id="bc545-119">`GetClassLayout` también producirá un error cuando se le llama con una clase de matriz.</span><span class="sxs-lookup"><span data-stu-id="bc545-119">`GetClassLayout` will also fail when called with an array class.</span></span>  
  
 <span data-ttu-id="bc545-120">Después de que `GetClassLayout` vuelva, debe comprobar que el búfer `rFieldOffset` era lo suficientemente grande como para contener todas las estructuras `COR_FIELD_OFFSET` disponibles.</span><span class="sxs-lookup"><span data-stu-id="bc545-120">After `GetClassLayout` returns, you must verify that the `rFieldOffset` buffer was large enough to contain all the available `COR_FIELD_OFFSET` structures.</span></span> <span data-ttu-id="bc545-121">Para ello, compare el valor al que `pcFieldOffset` apunta con el tamaño de `rFieldOffset` dividido por el tamaño de una estructura `COR_FIELD_OFFSET`.</span><span class="sxs-lookup"><span data-stu-id="bc545-121">To do this, compare the value that `pcFieldOffset` points to with the size of `rFieldOffset` divided by the size of a `COR_FIELD_OFFSET` structure.</span></span> <span data-ttu-id="bc545-122">Si `rFieldOffset` no es suficientemente grande, asigne un búfer `rFieldOffset` mayor, actualice `cFieldOffset` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetClassLayout`.</span><span class="sxs-lookup"><span data-stu-id="bc545-122">If `rFieldOffset` is not large enough, allocate a larger `rFieldOffset` buffer, update `cFieldOffset` with the new, larger size, and call `GetClassLayout` again.</span></span>  
  
 <span data-ttu-id="bc545-123">También tiene la opción de llamar primero a `GetClassLayout` con un búfer `rFieldOffset` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="bc545-123">Alternatively, you can first call `GetClassLayout` with a zero-length `rFieldOffset` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="bc545-124">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcFieldOffset` y volver a llamar a `GetClassLayout`.</span><span class="sxs-lookup"><span data-stu-id="bc545-124">You can then set the buffer size to the value returned in `pcFieldOffset` and call `GetClassLayout` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc545-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc545-125">Requirements</span></span>  

 <span data-ttu-id="bc545-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc545-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc545-127">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bc545-127">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bc545-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc545-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc545-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc545-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc545-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc545-130">See also</span></span>

- [<span data-ttu-id="bc545-131">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc545-131">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="bc545-132">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc545-132">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="bc545-133">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bc545-133">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="bc545-134">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bc545-134">Profiling</span></span>](index.md)
