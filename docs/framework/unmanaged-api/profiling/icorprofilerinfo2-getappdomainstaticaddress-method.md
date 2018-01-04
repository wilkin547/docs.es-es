---
title: "ICorProfilerInfo2::GetAppDomainStaticAddress (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetAppDomainStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type: apiref
caps.latest.revision: "22"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fad6cccc3992f001780bf8bd1a4c879dc6aa754
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="1495f-102">ICorProfilerInfo2::GetAppDomainStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="1495f-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="1495f-103">Obtiene la dirección del campo estático del dominio de aplicación especificada que se encuentra en el ámbito del dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="1495f-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1495f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1495f-104">Syntax</span></span>  
  
```  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1495f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1495f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="1495f-106">[in] El Id. de clase de la clase que contiene el campo estático de dominio de aplicación solicitada.</span><span class="sxs-lookup"><span data-stu-id="1495f-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="1495f-107">[in] El token de metadatos para el campo estático de dominio de aplicación solicitada.</span><span class="sxs-lookup"><span data-stu-id="1495f-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="1495f-108">[in] El Id. del dominio de aplicación que es el ámbito del campo estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="1495f-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="1495f-109">[out] Un puntero a la dirección del campo estático que está dentro del dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="1495f-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1495f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1495f-110">Remarks</span></span>  
 <span data-ttu-id="1495f-111">El `GetAppDomainStaticAddress` método puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1495f-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="1495f-112">Un HRESULT CORPROF_E_DATAINCOMPLETE si el campo estático especificado no se ha asignado una dirección en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="1495f-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="1495f-113">Las direcciones de los objetos que pueden estar en el montón de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1495f-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="1495f-114">Estas direcciones pueden no ser válidas después de recolección de elementos no utilizados, por lo que después de recolección de elementos no utilizados, los generadores de perfiles no deben suponer que son válidos.</span><span class="sxs-lookup"><span data-stu-id="1495f-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="1495f-115">Antes de que se complete el constructor de clase de una clase, `GetAppDomainStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque algunos de los campos estáticos pueden estar ya inicializados y objetos de la colección de elementos no utilizados de la raíz.</span><span class="sxs-lookup"><span data-stu-id="1495f-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1495f-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1495f-116">Requirements</span></span>  
 <span data-ttu-id="1495f-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1495f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1495f-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1495f-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1495f-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1495f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1495f-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1495f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1495f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1495f-121">See Also</span></span>  
 [<span data-ttu-id="1495f-122">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1495f-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="1495f-123">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1495f-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
