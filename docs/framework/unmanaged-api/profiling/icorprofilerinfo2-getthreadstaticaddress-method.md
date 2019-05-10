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
ms.openlocfilehash: de0e46f4703479daeb96cb83276ec14150125e7f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587445"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="3b0ce-102">ICorProfilerInfo2::GetThreadStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="3b0ce-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="3b0ce-103">Obtiene la dirección del campo estático de subproceso especificado que está en el ámbito del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="3b0ce-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b0ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b0ce-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b0ce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b0ce-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="3b0ce-106">[in] El identificador de la clase que contiene el campo de subproceso estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="3b0ce-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="3b0ce-107">[in] El token de metadatos para el campo de subproceso estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="3b0ce-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="3b0ce-108">[in] El identificador del subproceso que es el ámbito para el campo estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="3b0ce-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="3b0ce-109">[out] Un puntero a la dirección del campo estático que se encuentra dentro del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="3b0ce-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b0ce-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b0ce-110">Remarks</span></span>  
 <span data-ttu-id="3b0ce-111">El `GetThreadStaticAddress` método puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3b0ce-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="3b0ce-112">Un HRESULT CORPROF_E_DATAINCOMPLETE si el campo estático especificado no se ha asignado una dirección en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="3b0ce-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="3b0ce-113">Las direcciones de los objetos que pueden estar en el montón de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3b0ce-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="3b0ce-114">Estas direcciones pueden no ser válidas después de la recolección de elementos, después de que los generadores de perfiles de colección de elementos no utilizados no deben suponer que son válidos.</span><span class="sxs-lookup"><span data-stu-id="3b0ce-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="3b0ce-115">Antes de que se complete el constructor de clase de una clase, `GetThreadStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque ya se pueden inicializar algunos de los campos estáticos y los objetos de colección de elementos no utilizados de la raíz.</span><span class="sxs-lookup"><span data-stu-id="3b0ce-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b0ce-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b0ce-116">Requirements</span></span>  
 <span data-ttu-id="3b0ce-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b0ce-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b0ce-118">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3b0ce-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3b0ce-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b0ce-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b0ce-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b0ce-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b0ce-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b0ce-121">See also</span></span>

- [<span data-ttu-id="3b0ce-122">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b0ce-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="3b0ce-123">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b0ce-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
