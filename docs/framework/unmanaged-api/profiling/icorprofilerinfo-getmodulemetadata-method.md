---
title: "ICorProfilerInfo::GetModuleMetaData (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetModuleMetaData
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ad52460bcd6eb320e970cd0ce2078f2e93df353
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="59e0a-102">ICorProfilerInfo::GetModuleMetaData (Método)</span><span class="sxs-lookup"><span data-stu-id="59e0a-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>
<span data-ttu-id="59e0a-103">Obtiene una instancia de la interfaz de metadatos que se asigna para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="59e0a-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59e0a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59e0a-104">Syntax</span></span>  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59e0a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59e0a-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="59e0a-106">[in] El identificador del módulo al que se asignará la instancia de interfaz.</span><span class="sxs-lookup"><span data-stu-id="59e0a-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="59e0a-107">[in] Un valor de la [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeración que especifica el modo de abrir archivos de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="59e0a-107">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="59e0a-108">Solo el `ofRead`, `ofWrite` y `ofNoTransform` bits son válidos.</span><span class="sxs-lookup"><span data-stu-id="59e0a-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="59e0a-109">[in] La referencia del identificador (GUID) de la interfaz de metadatos cuya instancia se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="59e0a-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="59e0a-110">Vea [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) para obtener una lista de las interfaces.</span><span class="sxs-lookup"><span data-stu-id="59e0a-110">See [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="59e0a-111">[out] Un puntero a la dirección de la instancia de la interfaz de metadatos.</span><span class="sxs-lookup"><span data-stu-id="59e0a-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59e0a-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="59e0a-112">Remarks</span></span>  
 <span data-ttu-id="59e0a-113">Se puede pedir a los metadatos que se abrirá en modo de lectura/escritura, pero esto dará como resultado de una ejecución más lenta de metadatos del programa, porque los cambios realizan en los metadatos no se puede optimizar como si fueran del compilador.</span><span class="sxs-lookup"><span data-stu-id="59e0a-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="59e0a-114">Algunos módulos (por ejemplo, los módulos de recursos) no tienen metadatos.</span><span class="sxs-lookup"><span data-stu-id="59e0a-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="59e0a-115">En esos casos, `GetModuleMetaData` devolverá un valor HRESULT de S_FALSE y un valor null en *`ppOut`.</span><span class="sxs-lookup"><span data-stu-id="59e0a-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in *`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59e0a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59e0a-116">Requirements</span></span>  
 <span data-ttu-id="59e0a-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59e0a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59e0a-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="59e0a-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="59e0a-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59e0a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59e0a-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59e0a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59e0a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="59e0a-121">See Also</span></span>  
 [<span data-ttu-id="59e0a-122">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="59e0a-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
