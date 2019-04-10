---
title: ICorProfilerInfo2::GetContextStaticAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 46fd79931e7f2f05b1b17ebca3f8cff28c152ff4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221432"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="37926-102">ICorProfilerInfo2::GetContextStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="37926-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="37926-103">Obtiene la dirección para el campo estático de contexto especificado que está en el ámbito del contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="37926-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37926-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37926-104">Syntax</span></span>  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37926-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="37926-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="37926-106">[in] El identificador de la clase que contiene el campo estático de contexto solicitado.</span><span class="sxs-lookup"><span data-stu-id="37926-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="37926-107">[in] El token de metadatos para el campo estático de contexto solicitado.</span><span class="sxs-lookup"><span data-stu-id="37926-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="37926-108">[in] El identificador del contexto que es el ámbito para el campo estático de contexto solicitado.</span><span class="sxs-lookup"><span data-stu-id="37926-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="37926-109">[out] Un puntero a la dirección del campo estático que está dentro del contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="37926-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37926-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37926-110">Remarks</span></span>  
 <span data-ttu-id="37926-111">El `GetContextStaticAddress` método puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="37926-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="37926-112">Un HRESULT CORPROF_E_DATAINCOMPLETE si el campo estático especificado no se ha asignado una dirección en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="37926-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="37926-113">Las direcciones de los objetos que pueden estar en el montón de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="37926-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="37926-114">Estas direcciones pueden no ser válidas después de la recolección de elementos, por lo que después de la recolección de elementos, los generadores de perfiles no deben suponer que son válidos.</span><span class="sxs-lookup"><span data-stu-id="37926-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="37926-115">Antes de que se complete el constructor de clase de una clase, `GetContextStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque ya se pueden inicializar algunos de los campos estáticos y los objetos de colección de elementos no utilizados de la raíz.</span><span class="sxs-lookup"><span data-stu-id="37926-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37926-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37926-116">Requirements</span></span>  
 <span data-ttu-id="37926-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37926-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37926-118">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="37926-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="37926-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37926-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="37926-120">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="37926-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="37926-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="37926-121">See also</span></span>

- [<span data-ttu-id="37926-122">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37926-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="37926-123">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37926-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
