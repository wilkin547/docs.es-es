---
title: "ICorProfilerInfo::GetModuleInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetModuleInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetModuleInfo
helpviewer_keywords:
- GetModuleInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleInfo method [.NET Framework profiling]
ms.assetid: 5a90d16f-7929-4987-8f83-a631becf564d
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 23dc0208b4537530f18c2c282fbe8c3495ba301f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfogetmoduleinfo-method"></a><span data-ttu-id="c33ee-102">ICorProfilerInfo::GetModuleInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="c33ee-102">ICorProfilerInfo::GetModuleInfo Method</span></span>
<span data-ttu-id="c33ee-103">A partir de un identificador de módulo, devuelve el nombre de archivo del módulo y el identificador del ensamblado primario del módulo.</span><span class="sxs-lookup"><span data-stu-id="c33ee-103">Given a module ID, returns the file name of the module and the ID of the module's parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c33ee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c33ee-104">Syntax</span></span>  
  
```  
HRESULT GetModuleInfo(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c33ee-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c33ee-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="c33ee-106">[in] Identificador del módulo para el que se recuperará la información.</span><span class="sxs-lookup"><span data-stu-id="c33ee-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="c33ee-107">[out] Dirección base en la que se carga el módulo.</span><span class="sxs-lookup"><span data-stu-id="c33ee-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c33ee-108">[in] Longitud, en caracteres, del búfer de retorno `szName`.</span><span class="sxs-lookup"><span data-stu-id="c33ee-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c33ee-109">[out] Puntero a la longitud total de caracteres del nombre de archivo del módulo que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="c33ee-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="c33ee-110">[out] Búfer de caracteres anchos proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="c33ee-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="c33ee-111">Cuando el método vuelve, este búfer contiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="c33ee-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="c33ee-112">[out] Puntero al identificador del ensamblado primario del módulo.</span><span class="sxs-lookup"><span data-stu-id="c33ee-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c33ee-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c33ee-113">Remarks</span></span>  
 <span data-ttu-id="c33ee-114">Para los módulos dinámicos, el parámetro `szName` es una cadena vacía y la dirección base es 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="c33ee-114">For dynamic modules, the `szName` parameter is an empty string, and the base address is 0 (zero).</span></span>  
  
 <span data-ttu-id="c33ee-115">Aunque la `GetModuleInfo` puede llamar al método tan pronto como el identificador del módulo exista, el identificador del ensamblado primario no estará disponible hasta que el generador de perfiles reciba la [ICorProfilerCallback:: ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="c33ee-115">Although the `GetModuleInfo` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="c33ee-116">Cuando `GetModuleInfo` vuelve, debe comprobar que el búfer `szName` era lo suficientemente grande como para contener el nombre de archivo completo del módulo.</span><span class="sxs-lookup"><span data-stu-id="c33ee-116">When `GetModuleInfo` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="c33ee-117">Para ello, compare el valor al que `pcchName` apunta con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="c33ee-117">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="c33ee-118">Si `pcchName` apunta un valor mayor que `cchName`, asigne un búfer `szName` mayor, actualice `cchName` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetModuleInfo`.</span><span class="sxs-lookup"><span data-stu-id="c33ee-118">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo` again.</span></span>  
  
 <span data-ttu-id="c33ee-119">También puede llamar primero a `GetModuleInfo` con un búfer `szName` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="c33ee-119">Alternatively, you can first call `GetModuleInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="c33ee-120">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcchName` y volver a llamar a `GetModuleInfo`.</span><span class="sxs-lookup"><span data-stu-id="c33ee-120">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c33ee-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c33ee-121">Requirements</span></span>  
 <span data-ttu-id="c33ee-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c33ee-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c33ee-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c33ee-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c33ee-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c33ee-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c33ee-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c33ee-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c33ee-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="c33ee-126">See Also</span></span>  
 [<span data-ttu-id="c33ee-127">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c33ee-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="c33ee-128">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c33ee-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="c33ee-129">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c33ee-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)  
 [<span data-ttu-id="c33ee-130">GetModuleInfo2 (método)</span><span class="sxs-lookup"><span data-stu-id="c33ee-130">GetModuleInfo2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md)
