---
title: "ICorProfilerInfo3::GetModuleInfo2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo3.GetModuleInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetModuleInfo2
helpviewer_keywords:
- ICorProfilerInfo3::GetModuleInfo2 method [.NET Framework profiling]
- GetModuleInfo2 method [.NET Framework profiling]
ms.assetid: f1f6b8f3-dcfc-49e8-be76-ea50ea90d5a7
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 325db939c692a5dc7740e6cf813644ebffe9fc12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getmoduleinfo2-method"></a><span data-ttu-id="41881-102">ICorProfilerInfo3::GetModuleInfo2 (Método)</span><span class="sxs-lookup"><span data-stu-id="41881-102">ICorProfilerInfo3::GetModuleInfo2 Method</span></span>
<span data-ttu-id="41881-103">Dado un identificador de módulo, devuelve el nombre de archivo del módulo, el identificador del ensamblado primario del módulo y una máscara de bits que describe las propiedades del módulo.</span><span class="sxs-lookup"><span data-stu-id="41881-103">Given a module ID, returns the file name of the module, the ID of the module's parent assembly, and a bitmask that describes the properties of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41881-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41881-104">Syntax</span></span>  
  
```  
HRESULT GetModuleInfo2(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, annotation("__out_ecount_part(cchName, *pcchName)")]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
    [out] DWORD                 *pdwModuleFlags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41881-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41881-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="41881-106">[in] Identificador del módulo para el que se recuperará la información.</span><span class="sxs-lookup"><span data-stu-id="41881-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="41881-107">[out] Dirección base en la que se carga el módulo.</span><span class="sxs-lookup"><span data-stu-id="41881-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="41881-108">[in] Longitud, en caracteres, del búfer de retorno `szName`.</span><span class="sxs-lookup"><span data-stu-id="41881-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="41881-109">[out] Puntero a la longitud total de caracteres del nombre de archivo del módulo que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="41881-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="41881-110">[out] Búfer de caracteres anchos proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="41881-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="41881-111">Cuando el método vuelve, este búfer contiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="41881-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="41881-112">[out] Puntero al identificador del ensamblado primario del módulo.</span><span class="sxs-lookup"><span data-stu-id="41881-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
 `pdwModuleFlags`  
 <span data-ttu-id="41881-113">[out] Máscara de bits de la [COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) enumeración que especifican las propiedades del módulo.</span><span class="sxs-lookup"><span data-stu-id="41881-113">[out] A bitmask of values from the [COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) enumeration that specify the properties of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41881-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41881-114">Remarks</span></span>  
 <span data-ttu-id="41881-115">En el caso de los módulos dinámicos, el parámetro `szName` es el nombre de los metadatos del módulo, y la dirección base es 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="41881-115">For dynamic modules, the `szName` parameter is the metadata name of the module, and the base address is 0 (zero).</span></span> <span data-ttu-id="41881-116">El nombre de los metadatos es el valor de la columna Name de la tabla Module dentro de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="41881-116">The metadata name is the value in the Name column from the Module table inside metadata.</span></span> <span data-ttu-id="41881-117">Esto también se expone como la <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> propiedad al código administrado y como el `szName` parámetro de la [IMetaDataImport:: GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) método a código de cliente de metadatos no administrado.</span><span class="sxs-lookup"><span data-stu-id="41881-117">This is also exposed as the <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> property to managed code, and as the `szName` parameter of the [IMetaDataImport::GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) method to unmanaged metadata client code.</span></span>  
  
 <span data-ttu-id="41881-118">Aunque la `GetModuleInfo2` puede llamar al método tan pronto como el identificador del módulo exista, el identificador del ensamblado primario no estará disponible hasta que el generador de perfiles reciba la [ICorProfilerCallback:: ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="41881-118">Although the `GetModuleInfo2` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="41881-119">Cuando `GetModuleInfo2` vuelve, debe comprobar que el búfer `szName` era lo suficientemente grande como para contener el nombre de archivo completo del módulo.</span><span class="sxs-lookup"><span data-stu-id="41881-119">When `GetModuleInfo2` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="41881-120">Para ello, compare el valor al que `pcchName` apunta con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="41881-120">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="41881-121">Si `pcchName` apunta un valor mayor que `cchName`, asigne un búfer `szName` mayor, actualice `cchName` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetModuleInfo2`.</span><span class="sxs-lookup"><span data-stu-id="41881-121">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo2` again.</span></span>  
  
 <span data-ttu-id="41881-122">También puede llamar primero a `GetModuleInfo2` con un búfer `szName` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="41881-122">Alternatively, you can first call `GetModuleInfo2` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="41881-123">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcchName` y volver a llamar a `GetModuleInfo2`.</span><span class="sxs-lookup"><span data-stu-id="41881-123">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41881-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41881-124">Requirements</span></span>  
 <span data-ttu-id="41881-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41881-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41881-126">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41881-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="41881-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41881-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41881-128">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41881-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41881-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="41881-129">See Also</span></span>  
 [<span data-ttu-id="41881-130">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41881-130">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="41881-131">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="41881-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="41881-132">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="41881-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
