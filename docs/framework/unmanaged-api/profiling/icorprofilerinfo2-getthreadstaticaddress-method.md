---
title: ICorProfilerInfo2::GetThreadStaticAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a38c8323157cee866ac0ecab97532b9b72a932b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454133"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="aaed3-102">ICorProfilerInfo2::GetThreadStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="aaed3-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="aaed3-103">Obtiene la dirección del campo estático de subproceso especificado que se encuentra en el ámbito del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="aaed3-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaed3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aaed3-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aaed3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aaed3-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="aaed3-106">[in] El identificador de la clase que contiene el campo estático de subproceso solicitado.</span><span class="sxs-lookup"><span data-stu-id="aaed3-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="aaed3-107">[in] El token de metadatos para el campo estático de subproceso solicitado.</span><span class="sxs-lookup"><span data-stu-id="aaed3-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="aaed3-108">[in] El identificador del subproceso que constituye el ámbito del campo estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="aaed3-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="aaed3-109">[out] Un puntero a la dirección del campo estático que está dentro del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="aaed3-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aaed3-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aaed3-110">Remarks</span></span>  
 <span data-ttu-id="aaed3-111">El `GetThreadStaticAddress` método puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="aaed3-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="aaed3-112">Un HRESULT CORPROF_E_DATAINCOMPLETE si el campo estático especificado no se ha asignado una dirección en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="aaed3-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="aaed3-113">Las direcciones de los objetos que pueden estar en el montón de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="aaed3-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="aaed3-114">Estas direcciones pueden no ser válidas después de recolección de elementos no utilizados, por lo que tras los generadores de perfiles de recopilación de elementos no utilizados no deben suponer que son válidos.</span><span class="sxs-lookup"><span data-stu-id="aaed3-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="aaed3-115">Antes de que se complete el constructor de clase de una clase, `GetThreadStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque algunos de los campos estáticos pueden estar ya inicializados y objetos de la colección de elementos no utilizados de la raíz.</span><span class="sxs-lookup"><span data-stu-id="aaed3-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaed3-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aaed3-116">Requirements</span></span>  
 <span data-ttu-id="aaed3-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aaed3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaed3-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aaed3-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aaed3-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aaed3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aaed3-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaed3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaed3-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="aaed3-121">See Also</span></span>  
 [<span data-ttu-id="aaed3-122">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aaed3-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="aaed3-123">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aaed3-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
