---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5004de587f715a2f3958c36999e432d7d6e9f2fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632665"
---
# <a name="icorprofilerinfogetcodeinfo-method"></a><span data-ttu-id="17e90-102">ICorProfilerInfo::GetCodeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="17e90-102">ICorProfilerInfo::GetCodeInfo Method</span></span>
<span data-ttu-id="17e90-103">Obtiene la extensión del código nativo asociado al identificador de función especificado.</span><span class="sxs-lookup"><span data-stu-id="17e90-103">Gets the extent of native code associated with the specified function ID.</span></span>  
  
 <span data-ttu-id="17e90-104">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="17e90-104">This method is obsolete.</span></span> <span data-ttu-id="17e90-105">Use la [ICorProfilerInfo2:: Getcodeinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="17e90-105">Use the [ICorProfilerInfo2::GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17e90-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17e90-106">Syntax</span></span>  
  
```  
HRESULT GetCodeInfo(  
    [in]  FunctionID functionId,  
    [out] LPCBYTE    *pStart,  
    [out] ULONG      *pcSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17e90-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="17e90-107">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="17e90-108">[in] Identificador de función con la que está asociado el código nativo.</span><span class="sxs-lookup"><span data-stu-id="17e90-108">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `pStart`  
 <span data-ttu-id="17e90-109">[out] Puntero a una matriz de bytes que compone el código nativo de la función.</span><span class="sxs-lookup"><span data-stu-id="17e90-109">[out] A pointer to an array of bytes that compose the native code of the function.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="17e90-110">[out] Puntero a un entero que especifica el tamaño, en bytes, del código nativo.</span><span class="sxs-lookup"><span data-stu-id="17e90-110">[out] A pointer to an integer that specifies the size, in bytes, of the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17e90-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17e90-111">Remarks</span></span>  
 <span data-ttu-id="17e90-112">Para optimizar el rendimiento, el tiempo de ejecución en la versión 2.0 de .NET Framework divide el código nativo precompilado de una función en varias regiones.</span><span class="sxs-lookup"><span data-stu-id="17e90-112">To optimize performance, the runtime in the .NET Framework version 2.0 splits the precompiled, native code of a function into multiple regions.</span></span> <span data-ttu-id="17e90-113">Por consiguiente, el método `GetCodeInfo` está obsoleto en .NET Framework 2.0 porque no puede controlar la cantidad de código nativo de una función.</span><span class="sxs-lookup"><span data-stu-id="17e90-113">Consequently, the `GetCodeInfo` method is obsolete in the .NET Framework 2.0 because it is unable to handle the extent of a function's native code.</span></span> <span data-ttu-id="17e90-114">Los generadores de perfiles deben usar en su lugar el método `ICorProfilerInfo2::GetCodeInfo2`, que es más general.</span><span class="sxs-lookup"><span data-stu-id="17e90-114">Profilers should switch to using the more general `ICorProfilerInfo2::GetCodeInfo2` method instead.</span></span>  
  
 <span data-ttu-id="17e90-115">Esta función usa búferes asignados por el llamador.</span><span class="sxs-lookup"><span data-stu-id="17e90-115">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17e90-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17e90-116">Requirements</span></span>  
 <span data-ttu-id="17e90-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17e90-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17e90-118">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="17e90-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="17e90-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17e90-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17e90-120">**Versiones de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="17e90-120">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17e90-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="17e90-121">See also</span></span>
- [<span data-ttu-id="17e90-122">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="17e90-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="17e90-123">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="17e90-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="17e90-124">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="17e90-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
