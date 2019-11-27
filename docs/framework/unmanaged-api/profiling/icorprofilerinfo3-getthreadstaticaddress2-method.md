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
ms.openlocfilehash: ee44c89ec30edcb6233081f0757fa0f7b7191178
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449645"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a><span data-ttu-id="41f68-102">ICorProfilerInfo3::GetThreadStaticAddress2 (Método)</span><span class="sxs-lookup"><span data-stu-id="41f68-102">ICorProfilerInfo3::GetThreadStaticAddress2 Method</span></span>
<span data-ttu-id="41f68-103">Obtiene la dirección del campo estático de subproceso especificado que está en el ámbito del subproceso y del dominio de aplicación especificados.</span><span class="sxs-lookup"><span data-stu-id="41f68-103">Gets the address of the specified thread-static field that is in the scope of the specified thread and application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41f68-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41f68-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41f68-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41f68-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="41f68-106">de IDENTIFICADOR de la clase que contiene el campo estático de subproceso solicitado.</span><span class="sxs-lookup"><span data-stu-id="41f68-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="41f68-107">de Símbolo (token) de metadatos del campo estático de subproceso solicitado.</span><span class="sxs-lookup"><span data-stu-id="41f68-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="41f68-108">[in] Identificador de dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41f68-108">[in] The ID of the application domain.</span></span>  
  
 `threadId`  
 <span data-ttu-id="41f68-109">de IDENTIFICADOR del subproceso que es el ámbito del campo estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="41f68-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="41f68-110">enuncia Puntero a la dirección del campo estático que está dentro del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="41f68-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41f68-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41f68-111">Remarks</span></span>  
 <span data-ttu-id="41f68-112">El método `GetThreadStaticAddress2` puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="41f68-112">The `GetThreadStaticAddress2` method may return one of the following:</span></span>  
  
- <span data-ttu-id="41f68-113">CORPROF_E_DATAINCOMPLETE HRESULT si no se ha asignado una dirección al campo estático dado en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="41f68-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="41f68-114">Direcciones de los objetos que pueden estar en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="41f68-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="41f68-115">Estas direcciones pueden dejar de ser válidas después de la recolección de elementos no utilizados, por lo que después de la recolección de elementos no utilizados, los perfiles no deben suponer que son válidas.</span><span class="sxs-lookup"><span data-stu-id="41f68-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="41f68-116">Antes de que se complete el constructor de clase de una clase, `GetThreadStaticAddress2` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque es posible que algunos de los campos estáticos ya estén inicializados y contengan objetos de recolección de elementos no utilizados de raíz.</span><span class="sxs-lookup"><span data-stu-id="41f68-116">Before a class’s class constructor is completed, `GetThreadStaticAddress2` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
 <span data-ttu-id="41f68-117">El método [ICorProfilerInfo2:: getthreadstaticaddress (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) es similar al método `GetThreadStaticAddress2`, pero no acepta un argumento dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="41f68-117">The [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) method is similar to the `GetThreadStaticAddress2` method, but does not accept an application domain argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41f68-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41f68-118">Requirements</span></span>  
 <span data-ttu-id="41f68-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41f68-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41f68-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41f68-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="41f68-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41f68-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41f68-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41f68-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41f68-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="41f68-123">See also</span></span>

- [<span data-ttu-id="41f68-124">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41f68-124">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="41f68-125">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="41f68-125">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="41f68-126">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="41f68-126">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
