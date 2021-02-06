---
description: 'Más información acerca de: ICorProfilerInfo:: GetCodeInfo ((método)'
title: ICorProfilerInfo::GetCodeInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCodeInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCodeInfo
helpviewer_keywords:
- GetCodeInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetCodeInfo method [.NET Framework profiling]
ms.assetid: 90140b0f-a926-4a7e-b6fa-23e05f703cce
topic_type:
- apiref
ms.openlocfilehash: e965e9c21b7add0367b08f152bf509ad6b6ed4cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647666"
---
# <a name="icorprofilerinfogetcodeinfo-method"></a><span data-ttu-id="3a2f2-103">ICorProfilerInfo::GetCodeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="3a2f2-103">ICorProfilerInfo::GetCodeInfo Method</span></span>

<span data-ttu-id="3a2f2-104">Obtiene la extensión del código nativo asociado al identificador de función especificado.</span><span class="sxs-lookup"><span data-stu-id="3a2f2-104">Gets the extent of native code associated with the specified function ID.</span></span>  
  
 <span data-ttu-id="3a2f2-105">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="3a2f2-105">This method is obsolete.</span></span> <span data-ttu-id="3a2f2-106">Use en su lugar el método [ICorProfilerInfo2:: GetCodeInfo2 (](icorprofilerinfo2-getcodeinfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3a2f2-106">Use the [ICorProfilerInfo2::GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a2f2-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a2f2-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo(  
    [in]  FunctionID functionId,  
    [out] LPCBYTE    *pStart,  
    [out] ULONG      *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a2f2-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a2f2-108">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="3a2f2-109">[in] Identificador de función con la que está asociado el código nativo.</span><span class="sxs-lookup"><span data-stu-id="3a2f2-109">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `pStart`  
 <span data-ttu-id="3a2f2-110">[out] Puntero a una matriz de bytes que compone el código nativo de la función.</span><span class="sxs-lookup"><span data-stu-id="3a2f2-110">[out] A pointer to an array of bytes that compose the native code of the function.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="3a2f2-111">[out] Puntero a un entero que especifica el tamaño, en bytes, del código nativo.</span><span class="sxs-lookup"><span data-stu-id="3a2f2-111">[out] A pointer to an integer that specifies the size, in bytes, of the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a2f2-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3a2f2-112">Remarks</span></span>  

 <span data-ttu-id="3a2f2-113">Para optimizar el rendimiento, el tiempo de ejecución en la versión 2.0 de .NET Framework divide el código nativo precompilado de una función en varias regiones.</span><span class="sxs-lookup"><span data-stu-id="3a2f2-113">To optimize performance, the runtime in the .NET Framework version 2.0 splits the precompiled, native code of a function into multiple regions.</span></span> <span data-ttu-id="3a2f2-114">Por consiguiente, el método `GetCodeInfo` está obsoleto en .NET Framework 2.0 porque no puede controlar la cantidad de código nativo de una función.</span><span class="sxs-lookup"><span data-stu-id="3a2f2-114">Consequently, the `GetCodeInfo` method is obsolete in the .NET Framework 2.0 because it is unable to handle the extent of a function's native code.</span></span> <span data-ttu-id="3a2f2-115">Los generadores de perfiles deben usar en su lugar el método `ICorProfilerInfo2::GetCodeInfo2`, que es más general.</span><span class="sxs-lookup"><span data-stu-id="3a2f2-115">Profilers should switch to using the more general `ICorProfilerInfo2::GetCodeInfo2` method instead.</span></span>  
  
 <span data-ttu-id="3a2f2-116">Esta función usa búferes asignados por el llamador.</span><span class="sxs-lookup"><span data-stu-id="3a2f2-116">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a2f2-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a2f2-117">Requirements</span></span>  

 <span data-ttu-id="3a2f2-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a2f2-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a2f2-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3a2f2-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3a2f2-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a2f2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a2f2-121">**Versiones de .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="3a2f2-121">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a2f2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a2f2-122">See also</span></span>

- [<span data-ttu-id="3a2f2-123">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a2f2-123">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="3a2f2-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="3a2f2-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="3a2f2-125">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="3a2f2-125">Profiling</span></span>](index.md)
