---
title: ICorProfilerInfo2::GetAppDomainStaticAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8e1886a3e33b533eb525f5b35480a8a7d326da0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454598"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="cff10-102">ICorProfilerInfo2::GetAppDomainStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="cff10-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="cff10-103">Obtiene la dirección del campo estático del dominio de aplicación especificada que se encuentra en el ámbito del dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="cff10-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cff10-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cff10-104">Syntax</span></span>  
  
```  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cff10-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cff10-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="cff10-106">[in] El Id. de clase de la clase que contiene el campo estático de dominio de aplicación solicitada.</span><span class="sxs-lookup"><span data-stu-id="cff10-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="cff10-107">[in] El token de metadatos para el campo estático de dominio de aplicación solicitada.</span><span class="sxs-lookup"><span data-stu-id="cff10-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="cff10-108">[in] El Id. del dominio de aplicación que es el ámbito del campo estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="cff10-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="cff10-109">[out] Un puntero a la dirección del campo estático que está dentro del dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="cff10-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cff10-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cff10-110">Remarks</span></span>  
 <span data-ttu-id="cff10-111">El `GetAppDomainStaticAddress` método puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="cff10-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="cff10-112">Un HRESULT CORPROF_E_DATAINCOMPLETE si el campo estático especificado no se ha asignado una dirección en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="cff10-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="cff10-113">Las direcciones de los objetos que pueden estar en el montón de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cff10-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="cff10-114">Estas direcciones pueden no ser válidas después de recolección de elementos no utilizados, por lo que después de recolección de elementos no utilizados, los generadores de perfiles no deben suponer que son válidos.</span><span class="sxs-lookup"><span data-stu-id="cff10-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="cff10-115">Antes de que se complete el constructor de clase de una clase, `GetAppDomainStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque algunos de los campos estáticos pueden estar ya inicializados y objetos de la colección de elementos no utilizados de la raíz.</span><span class="sxs-lookup"><span data-stu-id="cff10-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cff10-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cff10-116">Requirements</span></span>  
 <span data-ttu-id="cff10-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cff10-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cff10-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cff10-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cff10-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cff10-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cff10-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cff10-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff10-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="cff10-121">See Also</span></span>  
 [<span data-ttu-id="cff10-122">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cff10-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="cff10-123">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cff10-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
