---
title: ICorProfilerInfo3::GetThreadStaticAddress2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 85f3ec6c2e0e452d3410437a7ec7cd45eb38cd5a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779851"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a><span data-ttu-id="11279-102">ICorProfilerInfo3::GetThreadStaticAddress2 (Método)</span><span class="sxs-lookup"><span data-stu-id="11279-102">ICorProfilerInfo3::GetThreadStaticAddress2 Method</span></span>
<span data-ttu-id="11279-103">Obtiene la dirección del campo estático de subproceso especificado que está en el ámbito del subproceso y del dominio de aplicación especificados.</span><span class="sxs-lookup"><span data-stu-id="11279-103">Gets the address of the specified thread-static field that is in the scope of the specified thread and application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11279-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11279-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11279-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11279-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="11279-106">[in] El identificador de la clase que contiene el campo de subproceso estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="11279-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="11279-107">[in] El token de metadatos para el campo de subproceso estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="11279-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="11279-108">[in] Identificador de dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="11279-108">[in] The ID of the application domain.</span></span>  
  
 `threadId`  
 <span data-ttu-id="11279-109">[in] El identificador del subproceso que es el ámbito para el campo estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="11279-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="11279-110">[out] Un puntero a la dirección del campo estático que se encuentra dentro del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="11279-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11279-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="11279-111">Remarks</span></span>  
 <span data-ttu-id="11279-112">El `GetThreadStaticAddress2` método puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="11279-112">The `GetThreadStaticAddress2` method may return one of the following:</span></span>  
  
- <span data-ttu-id="11279-113">Un HRESULT CORPROF_E_DATAINCOMPLETE si el campo estático especificado no se ha asignado una dirección en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="11279-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="11279-114">Las direcciones de los objetos que pueden estar en el montón de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="11279-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="11279-115">Estas direcciones pueden no ser válidas después de la recolección de elementos, por lo que después de la recolección de elementos, los generadores de perfiles no deben suponer que son válidos.</span><span class="sxs-lookup"><span data-stu-id="11279-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="11279-116">Antes de que se complete el constructor de clase de una clase, `GetThreadStaticAddress2` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque ya se pueden inicializar algunos de los campos estáticos y los objetos de colección de elementos no utilizados de la raíz.</span><span class="sxs-lookup"><span data-stu-id="11279-116">Before a class’s class constructor is completed, `GetThreadStaticAddress2` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
 <span data-ttu-id="11279-117">El [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) método es similar a la `GetThreadStaticAddress2` método, pero no acepta un argumento de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="11279-117">The [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) method is similar to the `GetThreadStaticAddress2` method, but does not accept an application domain argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11279-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11279-118">Requirements</span></span>  
 <span data-ttu-id="11279-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11279-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11279-120">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="11279-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="11279-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11279-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11279-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11279-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11279-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="11279-123">See also</span></span>

- [<span data-ttu-id="11279-124">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11279-124">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="11279-125">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="11279-125">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="11279-126">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="11279-126">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
