---
description: 'Más información acerca de: ICorProfilerInfo2:: Getcodeinfo2 ((método)'
title: ICorProfilerInfo2::GetCodeInfo2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetCodeInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetCodeInfo2
helpviewer_keywords:
- ICorProfilerInfo2::GetCodeInfo2 method [.NET Framework profiling]
- GetCodeInfo2 method [.NET Framework profiling]
ms.assetid: 532da6ee-7f0a-401b-a61e-fc47ec235d2e
topic_type:
- apiref
ms.openlocfilehash: 69b877b2dfe3bf23cd2b13417386c45d51de44d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760526"
---
# <a name="icorprofilerinfo2getcodeinfo2-method"></a><span data-ttu-id="2c821-103">ICorProfilerInfo2::GetCodeInfo2 (Método)</span><span class="sxs-lookup"><span data-stu-id="2c821-103">ICorProfilerInfo2::GetCodeInfo2 Method</span></span>

<span data-ttu-id="2c821-104">Obtiene las extensiones del código nativo asociado al `FunctionID` especificado.</span><span class="sxs-lookup"><span data-stu-id="2c821-104">Gets the extents of native code associated with the specified `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c821-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c821-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo2(  
    [in]  FunctionID functionID,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c821-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c821-106">Parameters</span></span>  

 `functionID`  
 <span data-ttu-id="2c821-107">[in] Identificador de función con la que está asociado el código nativo.</span><span class="sxs-lookup"><span data-stu-id="2c821-107">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="2c821-108">[in] Tamaño de la matriz `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="2c821-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="2c821-109">enuncia Puntero al número total de estructuras de [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) disponibles.</span><span class="sxs-lookup"><span data-stu-id="2c821-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="2c821-110">[out] Búfer proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="2c821-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="2c821-111">Después de que el método vuelva, contiene una matriz de estructuras `COR_PRF_CODE_INFO`, cada una de las cuales describe un bloque de código nativo.</span><span class="sxs-lookup"><span data-stu-id="2c821-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c821-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2c821-112">Remarks</span></span>  

 <span data-ttu-id="2c821-113">Las extensiones se clasifican por orden de desplazamiento creciente del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="2c821-113">The extents are sorted in order of increasing Microsoft intermediate language (MSIL) offset.</span></span>  
  
 <span data-ttu-id="2c821-114">Después de la devolución de `GetCodeInfo2`, debe comprobar que el búfer `codeInfos` era lo suficientemente grande como para contener todas las estructuras `COR_PRF_CODE_INFO`.</span><span class="sxs-lookup"><span data-stu-id="2c821-114">After `GetCodeInfo2` returns, you must verify that the `codeInfos` buffer was large enough to contain all the `COR_PRF_CODE_INFO` structures.</span></span> <span data-ttu-id="2c821-115">Para ello, compare el valor de `cCodeInfos` con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="2c821-115">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="2c821-116">Si `cCodeInfos` dividido entre el tamaño de una estructura `COR_PRF_CODE_INFO` es menor que `pcCodeInfos`, asigne un búfer `codeInfos` mayor, actualice `cCodeInfos` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetCodeInfo2`.</span><span class="sxs-lookup"><span data-stu-id="2c821-116">If `cCodeInfos` divided by the size of a `COR_PRF_CODE_INFO` structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo2` again.</span></span>  
  
 <span data-ttu-id="2c821-117">También tiene la opción de llamar primero a `GetCodeInfo2` con un búfer `codeInfos` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="2c821-117">Alternatively, you can first call `GetCodeInfo2` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="2c821-118">A continuación, puede establecer el tamaño del búfer `codeInfos` para el valor devuelto en `pcCodeInfos` multiplicándolo por el tamaño de una estructura `COR_PRF_CODE_INFO` y volver a llamar a `GetCodeInfo2`.</span><span class="sxs-lookup"><span data-stu-id="2c821-118">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a `COR_PRF_CODE_INFO` structure, and call `GetCodeInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c821-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c821-119">Requirements</span></span>  

 <span data-ttu-id="2c821-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c821-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c821-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2c821-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2c821-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c821-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c821-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c821-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c821-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c821-124">See also</span></span>

- [<span data-ttu-id="2c821-125">Método GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="2c821-125">GetCodeInfo3 Method</span></span>](icorprofilerinfo4-getcodeinfo3-method.md)
- [<span data-ttu-id="2c821-126">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c821-126">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="2c821-127">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2c821-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="2c821-128">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2c821-128">Profiling</span></span>](index.md)
