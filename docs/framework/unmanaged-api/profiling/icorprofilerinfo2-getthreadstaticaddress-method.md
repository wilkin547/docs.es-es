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
ms.openlocfilehash: d44eae4da70418e2d4f398b2bacee1fb53d55b60
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443051"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="beb9f-102">ICorProfilerInfo2::GetThreadStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="beb9f-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="beb9f-103">Obtiene la dirección del campo estático de subproceso especificado que está en el ámbito del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="beb9f-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beb9f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="beb9f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="beb9f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="beb9f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="beb9f-106">de IDENTIFICADOR de la clase que contiene el campo estático de subproceso solicitado.</span><span class="sxs-lookup"><span data-stu-id="beb9f-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="beb9f-107">de Símbolo (token) de metadatos del campo estático de subproceso solicitado.</span><span class="sxs-lookup"><span data-stu-id="beb9f-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="beb9f-108">de IDENTIFICADOR del subproceso que es el ámbito del campo estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="beb9f-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="beb9f-109">enuncia Puntero a la dirección del campo estático que está dentro del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="beb9f-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="beb9f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="beb9f-110">Remarks</span></span>  
 <span data-ttu-id="beb9f-111">El método `GetThreadStaticAddress` puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="beb9f-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="beb9f-112">CORPROF_E_DATAINCOMPLETE HRESULT si no se ha asignado una dirección al campo estático dado en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="beb9f-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="beb9f-113">Direcciones de los objetos que pueden estar en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="beb9f-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="beb9f-114">Estas direcciones pueden dejar de ser válidas después de la recolección de elementos no utilizados, por lo que después de que los perfiles de recolección de elementos no utilizados no asuman que son válidos.</span><span class="sxs-lookup"><span data-stu-id="beb9f-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="beb9f-115">Antes de que se complete el constructor de clase de una clase, `GetThreadStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque es posible que algunos de los campos estáticos ya estén inicializados y contengan objetos de recolección de elementos no utilizados de raíz.</span><span class="sxs-lookup"><span data-stu-id="beb9f-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beb9f-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="beb9f-116">Requirements</span></span>  
 <span data-ttu-id="beb9f-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beb9f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beb9f-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="beb9f-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="beb9f-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beb9f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="beb9f-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beb9f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb9f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="beb9f-121">See also</span></span>

- [<span data-ttu-id="beb9f-122">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="beb9f-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="beb9f-123">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="beb9f-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
