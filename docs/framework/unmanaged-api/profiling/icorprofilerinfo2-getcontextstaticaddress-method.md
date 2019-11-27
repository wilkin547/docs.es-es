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
ms.openlocfilehash: d5d7da343148d5f1c2aa9b2b639b094f8269199b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433205"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="cf66a-102">ICorProfilerInfo2::GetContextStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="cf66a-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="cf66a-103">Obtiene la dirección del campo estático de contexto especificado que está en el ámbito del contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="cf66a-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf66a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf66a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf66a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf66a-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="cf66a-106">de IDENTIFICADOR de la clase que contiene el campo de contexto estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="cf66a-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="cf66a-107">de El símbolo (token) de metadatos para el campo de contexto estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="cf66a-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="cf66a-108">de IDENTIFICADOR del contexto que es el ámbito del campo de contexto estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="cf66a-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="cf66a-109">enuncia Puntero a la dirección del campo estático que está dentro del contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="cf66a-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf66a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf66a-110">Remarks</span></span>  
 <span data-ttu-id="cf66a-111">El método `GetContextStaticAddress` puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="cf66a-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="cf66a-112">CORPROF_E_DATAINCOMPLETE HRESULT si no se ha asignado una dirección al campo estático dado en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="cf66a-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="cf66a-113">Direcciones de los objetos que pueden estar en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cf66a-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="cf66a-114">Estas direcciones pueden dejar de ser válidas después de la recolección de elementos no utilizados, por lo que después de la recolección de elementos no utilizados, los perfiles no deben suponer que son válidas.</span><span class="sxs-lookup"><span data-stu-id="cf66a-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="cf66a-115">Antes de que se complete el constructor de clase de una clase, `GetContextStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque es posible que algunos de los campos estáticos ya estén inicializados y contengan objetos de recolección de elementos no utilizados de raíz.</span><span class="sxs-lookup"><span data-stu-id="cf66a-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf66a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf66a-116">Requirements</span></span>  
 <span data-ttu-id="cf66a-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf66a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf66a-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf66a-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf66a-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf66a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf66a-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf66a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf66a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf66a-121">See also</span></span>

- [<span data-ttu-id="cf66a-122">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf66a-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="cf66a-123">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf66a-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
