---
description: 'Más información acerca de: ICorProfilerInfo:: Getmoduleinfo ((método)'
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
ms.openlocfilehash: 003f40e6637490be23e8bf87a6bac8ab76bc50e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647200"
---
# <a name="icorprofilerinfogetmoduleinfo-method"></a><span data-ttu-id="42096-103">ICorProfilerInfo::GetModuleInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="42096-103">ICorProfilerInfo::GetModuleInfo Method</span></span>

<span data-ttu-id="42096-104">A partir de un identificador de módulo, devuelve el nombre de archivo del módulo y el identificador del ensamblado primario del módulo.</span><span class="sxs-lookup"><span data-stu-id="42096-104">Given a module ID, returns the file name of the module and the ID of the module's parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42096-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42096-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="42096-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42096-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="42096-107">[in] Identificador del módulo para el que se recuperará la información.</span><span class="sxs-lookup"><span data-stu-id="42096-107">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="42096-108">[out] Dirección base en la que se carga el módulo.</span><span class="sxs-lookup"><span data-stu-id="42096-108">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="42096-109">[in] Longitud, en caracteres, del búfer de retorno `szName`.</span><span class="sxs-lookup"><span data-stu-id="42096-109">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="42096-110">[out] Puntero a la longitud total de caracteres del nombre de archivo del módulo que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="42096-110">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="42096-111">[out] Búfer de caracteres anchos proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="42096-111">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="42096-112">Cuando el método vuelve, este búfer contiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="42096-112">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="42096-113">[out] Puntero al identificador del ensamblado primario del módulo.</span><span class="sxs-lookup"><span data-stu-id="42096-113">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42096-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="42096-114">Remarks</span></span>  

 <span data-ttu-id="42096-115">Para los módulos dinámicos, el parámetro `szName` es una cadena vacía y la dirección base es 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="42096-115">For dynamic modules, the `szName` parameter is an empty string, and the base address is 0 (zero).</span></span>  
  
 <span data-ttu-id="42096-116">Aunque `GetModuleInfo` se puede llamar al método en cuanto existe el identificador del módulo, el identificador del ensamblado primario no estará disponible hasta que el generador de perfiles reciba la devolución de llamada [ICorProfilerCallback:: moduleattachedtoassembly (](icorprofilercallback-moduleattachedtoassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="42096-116">Although the `GetModuleInfo` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="42096-117">Cuando `GetModuleInfo` vuelve, debe comprobar que el búfer `szName` era lo suficientemente grande como para contener el nombre de archivo completo del módulo.</span><span class="sxs-lookup"><span data-stu-id="42096-117">When `GetModuleInfo` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="42096-118">Para ello, compare el valor al que `pcchName` apunta con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="42096-118">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="42096-119">Si `pcchName` apunta un valor mayor que `cchName`, asigne un búfer `szName` mayor, actualice `cchName` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetModuleInfo`.</span><span class="sxs-lookup"><span data-stu-id="42096-119">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo` again.</span></span>  
  
 <span data-ttu-id="42096-120">También tiene la opción de llamar primero a `GetModuleInfo` con un búfer `szName` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="42096-120">Alternatively, you can first call `GetModuleInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="42096-121">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcchName` y volver a llamar a `GetModuleInfo`.</span><span class="sxs-lookup"><span data-stu-id="42096-121">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42096-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42096-122">Requirements</span></span>  

 <span data-ttu-id="42096-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42096-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42096-124">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42096-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42096-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42096-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42096-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42096-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42096-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="42096-127">See also</span></span>

- [<span data-ttu-id="42096-128">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="42096-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="42096-129">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="42096-129">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="42096-130">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="42096-130">Profiling</span></span>](index.md)
- [<span data-ttu-id="42096-131">Método GetModuleInfo2</span><span class="sxs-lookup"><span data-stu-id="42096-131">GetModuleInfo2 Method</span></span>](icorprofilerinfo3-getmoduleinfo2-method.md)
