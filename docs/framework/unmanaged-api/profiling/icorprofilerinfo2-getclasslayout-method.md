---
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
ms.openlocfilehash: 85319a45861b2b48f7690f69bb8f9f9469af014c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862807"
---
# <a name="icorprofilerinfo2getclasslayout-method"></a><span data-ttu-id="b34db-102">ICorProfilerInfo2::GetClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="b34db-102">ICorProfilerInfo2::GetClassLayout Method</span></span>
<span data-ttu-id="b34db-103">Obtiene información sobre la distribución, en memoria, de los campos definidos por la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="b34db-103">Gets information about the layout, in memory, of the fields defined by the specified class.</span></span> <span data-ttu-id="b34db-104">Es decir, este método obtiene los desplazamientos de los campos de la clase.</span><span class="sxs-lookup"><span data-stu-id="b34db-104">That is, this method gets the offsets of the class's fields.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b34db-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b34db-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout(  
    [in]  ClassID classID,  
    [in, out] COR_FIELD_OFFSET rFieldOffset[],  
    [in]  ULONG cFieldOffset,  
    [out] ULONG *pcFieldOffset,  
    [out] ULONG *pulClassSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b34db-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="b34db-106">Parameters</span></span>  
 `classID`  
 <span data-ttu-id="b34db-107">[in] Identificador de la clase para la cual se recuperará la distribución.</span><span class="sxs-lookup"><span data-stu-id="b34db-107">[in] The ID of the class for which the layout will be retrieved.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="b34db-108">[in, out] Matriz de estructuras de [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) , cada una de las cuales contiene los tokens y desplazamientos de los campos de la clase.</span><span class="sxs-lookup"><span data-stu-id="b34db-108">[in, out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which contains the tokens and offsets of the class's fields.</span></span>  
  
 `cFieldOffset`  
 <span data-ttu-id="b34db-109">[in] Tamaño de la matriz `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="b34db-109">[in] The size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="b34db-110">[out] Puntero al número total de elementos disponibles.</span><span class="sxs-lookup"><span data-stu-id="b34db-110">[out] A pointer to the total number of available elements.</span></span> <span data-ttu-id="b34db-111">Si `cFieldOffset` es 0, este valor indica el número de elementos necesario.</span><span class="sxs-lookup"><span data-stu-id="b34db-111">If `cFieldOffset` is 0, this value indicates the number of elements needed.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="b34db-112">[out] Puntero a una ubicación que contiene el tamaño, en bytes, de la clase.</span><span class="sxs-lookup"><span data-stu-id="b34db-112">[out] A pointer to a location that contains the size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b34db-113">Notas</span><span class="sxs-lookup"><span data-stu-id="b34db-113">Remarks</span></span>  
 <span data-ttu-id="b34db-114">El método `GetClassLayout` solo devuelve los campos definidos por la propia clase.</span><span class="sxs-lookup"><span data-stu-id="b34db-114">The `GetClassLayout` method returns only the fields defined by the class itself.</span></span> <span data-ttu-id="b34db-115">Si la clase primaria de la clase también tiene campos definidos, el generador de perfiles debe llamar a `GetClassLayout` en la clase primaria para obtener dichos campos.</span><span class="sxs-lookup"><span data-stu-id="b34db-115">If the class's parent class has defined fields as well, the profiler must call `GetClassLayout` on the parent class to obtain those fields.</span></span>  
  
 <span data-ttu-id="b34db-116">Si usa `GetClassLayout` con clases de cadena, el método producirá un error con el código E_INVALIDARG.</span><span class="sxs-lookup"><span data-stu-id="b34db-116">If you use `GetClassLayout` with string classes, the method will fail with error code E_INVALIDARG.</span></span> <span data-ttu-id="b34db-117">Use [ICorProfilerInfo2:: GetStringLayout (](icorprofilerinfo2-getstringlayout-method.md) para obtener información sobre el diseño de una cadena.</span><span class="sxs-lookup"><span data-stu-id="b34db-117">Use [ICorProfilerInfo2::GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) to get information about the layout of a string.</span></span> <span data-ttu-id="b34db-118">`GetClassLayout` también producirá un error cuando se le llama con una clase de matriz.</span><span class="sxs-lookup"><span data-stu-id="b34db-118">`GetClassLayout` will also fail when called with an array class.</span></span>  
  
 <span data-ttu-id="b34db-119">Después de que `GetClassLayout` vuelva, debe comprobar que el búfer `rFieldOffset` era lo suficientemente grande como para contener todas las estructuras `COR_FIELD_OFFSET` disponibles.</span><span class="sxs-lookup"><span data-stu-id="b34db-119">After `GetClassLayout` returns, you must verify that the `rFieldOffset` buffer was large enough to contain all the available `COR_FIELD_OFFSET` structures.</span></span> <span data-ttu-id="b34db-120">Para ello, compare el valor al que `pcFieldOffset` apunta con el tamaño de `rFieldOffset` dividido por el tamaño de una estructura `COR_FIELD_OFFSET`.</span><span class="sxs-lookup"><span data-stu-id="b34db-120">To do this, compare the value that `pcFieldOffset` points to with the size of `rFieldOffset` divided by the size of a `COR_FIELD_OFFSET` structure.</span></span> <span data-ttu-id="b34db-121">Si `rFieldOffset` no es suficientemente grande, asigne un búfer `rFieldOffset` mayor, actualice `cFieldOffset` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetClassLayout`.</span><span class="sxs-lookup"><span data-stu-id="b34db-121">If `rFieldOffset` is not large enough, allocate a larger `rFieldOffset` buffer, update `cFieldOffset` with the new, larger size, and call `GetClassLayout` again.</span></span>  
  
 <span data-ttu-id="b34db-122">También tiene la opción de llamar primero a `GetClassLayout` con un búfer `rFieldOffset` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="b34db-122">Alternatively, you can first call `GetClassLayout` with a zero-length `rFieldOffset` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="b34db-123">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcFieldOffset` y volver a llamar a `GetClassLayout`.</span><span class="sxs-lookup"><span data-stu-id="b34db-123">You can then set the buffer size to the value returned in `pcFieldOffset` and call `GetClassLayout` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b34db-124">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b34db-124">Requirements</span></span>  
 <span data-ttu-id="b34db-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b34db-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b34db-126">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b34db-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b34db-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b34db-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b34db-128">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b34db-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b34db-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="b34db-129">See also</span></span>

- [<span data-ttu-id="b34db-130">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b34db-130">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="b34db-131">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b34db-131">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="b34db-132">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b34db-132">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b34db-133">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b34db-133">Profiling</span></span>](index.md)
