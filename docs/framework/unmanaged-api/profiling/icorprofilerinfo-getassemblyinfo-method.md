---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3579020ce268cd59a091e685fae2e97b3191c55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456128"
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a><span data-ttu-id="6277c-102">ICorProfilerInfo::GetAssemblyInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="6277c-102">ICorProfilerInfo::GetAssemblyInfo Method</span></span>
<span data-ttu-id="6277c-103">Acepta un identificador de ensamblado y devuelve el nombre del ensamblado y el identificador de su módulo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="6277c-103">Accepts an assembly ID, and returns the assembly's name and the ID of its manifest module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6277c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6277c-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6277c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6277c-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="6277c-106">[in] Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6277c-106">[in] The identifier of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="6277c-107">[in] Longitud, en caracteres, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="6277c-107">[in] The length, in characters, of `szName`.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6277c-108">[out] Puntero a la longitud total de caracteres del nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6277c-108">[out] A pointer to the total character length of the assembly's name.</span></span>  
  
 `szName`  
 <span data-ttu-id="6277c-109">[out] Búfer de caracteres anchos proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="6277c-109">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="6277c-110">Cuando se devuelve la función, contiene el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6277c-110">When the function returns, it will contain the assembly's name.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="6277c-111">[out] Puntero al identificador del dominio de aplicación que contiene el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6277c-111">[out] A pointer to the ID of the application domain that contains the assembly.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="6277c-112">[out] Puntero al identificador del módulo del manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6277c-112">[out] A pointer to the ID of the assembly's manifest module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6277c-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6277c-113">Remarks</span></span>  
 <span data-ttu-id="6277c-114">Tras la devolución de este método, debe comprobar que el búfer `szName` era lo suficientemente grande como para contener el nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6277c-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the assembly.</span></span> <span data-ttu-id="6277c-115">Para ello, compare el valor que señala `pcchName` con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="6277c-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="6277c-116">Si `pcchName` apunta un valor mayor que `cchName`, asigne un búfer `szName` mayor, actualice `cchName` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetAssemblyInfo`.</span><span class="sxs-lookup"><span data-stu-id="6277c-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAssemblyInfo` again.</span></span>  
  
 <span data-ttu-id="6277c-117">También tiene la opción de llamar primero a `GetAssemblyInfo` con un búfer `szName` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="6277c-117">Alternatively, you can first call `GetAssemblyInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="6277c-118">A continuación, puede ajustar el tamaño del búfer en función del valor devuelto en `pcchName` y volver a llamar a `GetAssemblyInfo`.</span><span class="sxs-lookup"><span data-stu-id="6277c-118">You can then adjust the buffer size based on the value returned in `pcchName` and call `GetAssemblyInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6277c-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6277c-119">Requirements</span></span>  
 <span data-ttu-id="6277c-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6277c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6277c-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6277c-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6277c-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6277c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6277c-123">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6277c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6277c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="6277c-124">See Also</span></span>  
 [<span data-ttu-id="6277c-125">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6277c-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="6277c-126">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="6277c-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="6277c-127">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="6277c-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
