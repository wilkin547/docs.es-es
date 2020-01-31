---
title: ICorProfilerInfo3::GetModuleInfo2 (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 96cde35c7151bb7ce58715f2826feaa59b30efab
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862313"
---
# <a name="icorprofilerinfo3getmoduleinfo2-method"></a><span data-ttu-id="4565f-102">ICorProfilerInfo3::GetModuleInfo2 (Método)</span><span class="sxs-lookup"><span data-stu-id="4565f-102">ICorProfilerInfo3::GetModuleInfo2 Method</span></span>
<span data-ttu-id="4565f-103">Dado un identificador de módulo, devuelve el nombre de archivo del módulo, el identificador del ensamblado primario del módulo y una máscara de bits que describe las propiedades del módulo.</span><span class="sxs-lookup"><span data-stu-id="4565f-103">Given a module ID, returns the file name of the module, the ID of the module's parent assembly, and a bitmask that describes the properties of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4565f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4565f-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="4565f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4565f-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="4565f-106">[in] Identificador del módulo para el que se recuperará la información.</span><span class="sxs-lookup"><span data-stu-id="4565f-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="4565f-107">[out] Dirección base en la que se carga el módulo.</span><span class="sxs-lookup"><span data-stu-id="4565f-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4565f-108">[in] Longitud, en caracteres, del búfer de retorno `szName`.</span><span class="sxs-lookup"><span data-stu-id="4565f-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4565f-109">[out] Puntero a la longitud total de caracteres del nombre de archivo del módulo que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="4565f-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="4565f-110">[out] Búfer de caracteres anchos proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="4565f-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="4565f-111">Cuando el método vuelve, este búfer contiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="4565f-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="4565f-112">[out] Puntero al identificador del ensamblado primario del módulo.</span><span class="sxs-lookup"><span data-stu-id="4565f-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
 `pdwModuleFlags`  
 <span data-ttu-id="4565f-113">enuncia Máscara de máscara de valores de la enumeración [COR_PRF_MODULE_FLAGS](cor-prf-module-flags-enumeration.md) que especifican las propiedades del módulo.</span><span class="sxs-lookup"><span data-stu-id="4565f-113">[out] A bitmask of values from the [COR_PRF_MODULE_FLAGS](cor-prf-module-flags-enumeration.md) enumeration that specify the properties of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4565f-114">Notas</span><span class="sxs-lookup"><span data-stu-id="4565f-114">Remarks</span></span>  
 <span data-ttu-id="4565f-115">En el caso de los módulos dinámicos, el parámetro `szName` es el nombre de los metadatos del módulo, y la dirección base es 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="4565f-115">For dynamic modules, the `szName` parameter is the metadata name of the module, and the base address is 0 (zero).</span></span> <span data-ttu-id="4565f-116">El nombre de los metadatos es el valor de la columna Name de la tabla Module dentro de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="4565f-116">The metadata name is the value in the Name column from the Module table inside metadata.</span></span> <span data-ttu-id="4565f-117">También se expone como la propiedad <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> a código administrado y como el parámetro `szName` del método [IMetaDataImport:: GetScopeProps (](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) al código de cliente de metadatos no administrados.</span><span class="sxs-lookup"><span data-stu-id="4565f-117">This is also exposed as the <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> property to managed code, and as the `szName` parameter of the [IMetaDataImport::GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) method to unmanaged metadata client code.</span></span>  
  
 <span data-ttu-id="4565f-118">Aunque se puede llamar al método `GetModuleInfo2` en cuanto existe el identificador del módulo, el identificador del ensamblado primario no estará disponible hasta que el generador de perfiles reciba la devolución de llamada [ICorProfilerCallback:: moduleattachedtoassembly (](icorprofilercallback-moduleattachedtoassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4565f-118">Although the `GetModuleInfo2` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="4565f-119">Cuando `GetModuleInfo2` vuelve, debe comprobar que el búfer `szName` era lo suficientemente grande como para contener el nombre de archivo completo del módulo.</span><span class="sxs-lookup"><span data-stu-id="4565f-119">When `GetModuleInfo2` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="4565f-120">Para ello, compare el valor al que `pcchName` apunta con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="4565f-120">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="4565f-121">Si `pcchName` apunta un valor mayor que `cchName`, asigne un búfer `szName` mayor, actualice `cchName` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetModuleInfo2`.</span><span class="sxs-lookup"><span data-stu-id="4565f-121">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo2` again.</span></span>  
  
 <span data-ttu-id="4565f-122">También tiene la opción de llamar primero a `GetModuleInfo2` con un búfer `szName` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="4565f-122">Alternatively, you can first call `GetModuleInfo2` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="4565f-123">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcchName` y volver a llamar a `GetModuleInfo2`.</span><span class="sxs-lookup"><span data-stu-id="4565f-123">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4565f-124">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4565f-124">Requirements</span></span>  
 <span data-ttu-id="4565f-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4565f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4565f-126">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4565f-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4565f-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4565f-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4565f-128">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4565f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4565f-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4565f-129">See also</span></span>

- [<span data-ttu-id="4565f-130">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4565f-130">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="4565f-131">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4565f-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="4565f-132">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4565f-132">Profiling</span></span>](index.md)
