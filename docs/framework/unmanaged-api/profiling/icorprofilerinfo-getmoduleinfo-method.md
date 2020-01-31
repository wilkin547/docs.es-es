---
title: ICorProfilerInfo::GetModuleInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleInfo
helpviewer_keywords:
- GetModuleInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleInfo method [.NET Framework profiling]
ms.assetid: 5a90d16f-7929-4987-8f83-a631becf564d
topic_type:
- apiref
ms.openlocfilehash: 25c5568e4cae0ead82b59b09dbbb9a11e4bc2df2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863444"
---
# <a name="icorprofilerinfogetmoduleinfo-method"></a><span data-ttu-id="2d6ed-102">ICorProfilerInfo::GetModuleInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="2d6ed-102">ICorProfilerInfo::GetModuleInfo Method</span></span>
<span data-ttu-id="2d6ed-103">A partir de un identificador de módulo, devuelve el nombre de archivo del módulo y el identificador del ensamblado primario del módulo.</span><span class="sxs-lookup"><span data-stu-id="2d6ed-103">Given a module ID, returns the file name of the module and the ID of the module's parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d6ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d6ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleInfo(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d6ed-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2d6ed-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="2d6ed-106">[in] Identificador del módulo para el que se recuperará la información.</span><span class="sxs-lookup"><span data-stu-id="2d6ed-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="2d6ed-107">[out] Dirección base en la que se carga el módulo.</span><span class="sxs-lookup"><span data-stu-id="2d6ed-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2d6ed-108">[in] Longitud, en caracteres, del búfer de retorno `szName`.</span><span class="sxs-lookup"><span data-stu-id="2d6ed-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2d6ed-109">[out] Puntero a la longitud total de caracteres del nombre de archivo del módulo que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="2d6ed-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="2d6ed-110">[out] Búfer de caracteres anchos proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="2d6ed-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="2d6ed-111">Cuando el método vuelve, este búfer contiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="2d6ed-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="2d6ed-112">[out] Puntero al identificador del ensamblado primario del módulo.</span><span class="sxs-lookup"><span data-stu-id="2d6ed-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d6ed-113">Notas</span><span class="sxs-lookup"><span data-stu-id="2d6ed-113">Remarks</span></span>  
 <span data-ttu-id="2d6ed-114">Para los módulos dinámicos, el parámetro `szName` es una cadena vacía y la dirección base es 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="2d6ed-114">For dynamic modules, the `szName` parameter is an empty string, and the base address is 0 (zero).</span></span>  
  
 <span data-ttu-id="2d6ed-115">Aunque se puede llamar al método `GetModuleInfo` en cuanto existe el identificador del módulo, el identificador del ensamblado primario no estará disponible hasta que el generador de perfiles reciba la devolución de llamada [ICorProfilerCallback:: moduleattachedtoassembly (](icorprofilercallback-moduleattachedtoassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2d6ed-115">Although the `GetModuleInfo` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="2d6ed-116">Cuando `GetModuleInfo` vuelve, debe comprobar que el búfer `szName` era lo suficientemente grande como para contener el nombre de archivo completo del módulo.</span><span class="sxs-lookup"><span data-stu-id="2d6ed-116">When `GetModuleInfo` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="2d6ed-117">Para ello, compare el valor al que `pcchName` apunta con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="2d6ed-117">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="2d6ed-118">Si `pcchName` apunta un valor mayor que `cchName`, asigne un búfer `szName` mayor, actualice `cchName` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetModuleInfo`.</span><span class="sxs-lookup"><span data-stu-id="2d6ed-118">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo` again.</span></span>  
  
 <span data-ttu-id="2d6ed-119">También tiene la opción de llamar primero a `GetModuleInfo` con un búfer `szName` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="2d6ed-119">Alternatively, you can first call `GetModuleInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="2d6ed-120">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcchName` y volver a llamar a `GetModuleInfo`.</span><span class="sxs-lookup"><span data-stu-id="2d6ed-120">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d6ed-121">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2d6ed-121">Requirements</span></span>  
 <span data-ttu-id="2d6ed-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d6ed-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d6ed-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d6ed-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d6ed-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d6ed-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d6ed-125">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d6ed-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d6ed-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d6ed-126">See also</span></span>

- [<span data-ttu-id="2d6ed-127">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d6ed-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="2d6ed-128">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2d6ed-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="2d6ed-129">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2d6ed-129">Profiling</span></span>](index.md)
- [<span data-ttu-id="2d6ed-130">GetModuleInfo2 (método)</span><span class="sxs-lookup"><span data-stu-id="2d6ed-130">GetModuleInfo2 Method</span></span>](icorprofilerinfo3-getmoduleinfo2-method.md)
