---
description: 'Más información acerca de: ICorProfilerInfo:: GetAssemblyInfo ((método)'
title: ICorProfilerInfo::GetAssemblyInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAssemblyInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type:
- apiref
ms.openlocfilehash: 64e94031e0e4fc5f768e94b83e4e97c3a9a7cb61
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647874"
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a><span data-ttu-id="9c152-103">ICorProfilerInfo::GetAssemblyInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="9c152-103">ICorProfilerInfo::GetAssemblyInfo Method</span></span>

<span data-ttu-id="9c152-104">Acepta un identificador de ensamblado y devuelve el nombre del ensamblado y el identificador de su módulo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="9c152-104">Accepts an assembly ID, and returns the assembly's name and the ID of its manifest module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c152-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c152-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c152-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9c152-106">Parameters</span></span>  

 `assemblyId`  
 <span data-ttu-id="9c152-107">[in] Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9c152-107">[in] The identifier of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="9c152-108">[in] Longitud, en caracteres, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="9c152-108">[in] The length, in characters, of `szName`.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9c152-109">[out] Puntero a la longitud total de caracteres del nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9c152-109">[out] A pointer to the total character length of the assembly's name.</span></span>  
  
 `szName`  
 <span data-ttu-id="9c152-110">[out] Búfer de caracteres anchos proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="9c152-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="9c152-111">Cuando se devuelve la función, contiene el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9c152-111">When the function returns, it will contain the assembly's name.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="9c152-112">[out] Puntero al identificador del dominio de aplicación que contiene el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9c152-112">[out] A pointer to the ID of the application domain that contains the assembly.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="9c152-113">[out] Puntero al identificador del módulo del manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9c152-113">[out] A pointer to the ID of the assembly's manifest module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c152-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9c152-114">Remarks</span></span>  

 <span data-ttu-id="9c152-115">Tras la devolución de este método, debe comprobar que el búfer `szName` era lo suficientemente grande como para contener el nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9c152-115">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the assembly.</span></span> <span data-ttu-id="9c152-116">Para ello, compare el valor al que `pcchName` apunta con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="9c152-116">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="9c152-117">Si `pcchName` apunta un valor mayor que `cchName`, asigne un búfer `szName` mayor, actualice `cchName` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetAssemblyInfo`.</span><span class="sxs-lookup"><span data-stu-id="9c152-117">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAssemblyInfo` again.</span></span>  
  
 <span data-ttu-id="9c152-118">También tiene la opción de llamar primero a `GetAssemblyInfo` con un búfer `szName` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="9c152-118">Alternatively, you can first call `GetAssemblyInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="9c152-119">A continuación, puede ajustar el tamaño del búfer en función del valor devuelto en `pcchName` y volver a llamar a `GetAssemblyInfo`.</span><span class="sxs-lookup"><span data-stu-id="9c152-119">You can then adjust the buffer size based on the value returned in `pcchName` and call `GetAssemblyInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c152-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c152-120">Requirements</span></span>  

 <span data-ttu-id="9c152-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c152-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c152-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9c152-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c152-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c152-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c152-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c152-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c152-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c152-125">See also</span></span>

- [<span data-ttu-id="9c152-126">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c152-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="9c152-127">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9c152-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="9c152-128">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9c152-128">Profiling</span></span>](index.md)
