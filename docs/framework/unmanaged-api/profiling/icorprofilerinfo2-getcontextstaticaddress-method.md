---
description: 'Más información acerca de: ICorProfilerInfo2:: GetContextStaticAddress ((método)'
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
ms.openlocfilehash: 7ea8b81c8b1dba4577e070eda68e760cc39f9131
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760519"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="24e79-103">ICorProfilerInfo2::GetContextStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="24e79-103">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>

<span data-ttu-id="24e79-104">Obtiene la dirección del campo estático de contexto especificado que está en el ámbito del contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="24e79-104">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24e79-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24e79-105">Syntax</span></span>  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24e79-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24e79-106">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="24e79-107">de IDENTIFICADOR de la clase que contiene el campo de contexto estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="24e79-107">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="24e79-108">de El símbolo (token) de metadatos para el campo de contexto estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="24e79-108">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="24e79-109">de IDENTIFICADOR del contexto que es el ámbito del campo de contexto estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="24e79-109">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="24e79-110">enuncia Puntero a la dirección del campo estático que está dentro del contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="24e79-110">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24e79-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="24e79-111">Remarks</span></span>  

 <span data-ttu-id="24e79-112">El `GetContextStaticAddress` método puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="24e79-112">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="24e79-113">CORPROF_E_DATAINCOMPLETE HRESULT si no se ha asignado una dirección al campo estático dado en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="24e79-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="24e79-114">Direcciones de los objetos que pueden estar en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="24e79-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="24e79-115">Estas direcciones pueden dejar de ser válidas después de la recolección de elementos no utilizados, por lo que después de la recolección de elementos no utilizados, los perfiles no deben suponer que son válidas.</span><span class="sxs-lookup"><span data-stu-id="24e79-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="24e79-116">Antes de que se complete el constructor de clase de una clase, `GetContextStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE de todos sus campos estáticos, aunque es posible que algunos de los campos estáticos ya estén inicializados y contengan objetos de recolección de elementos no utilizados de raíz.</span><span class="sxs-lookup"><span data-stu-id="24e79-116">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24e79-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24e79-117">Requirements</span></span>  

 <span data-ttu-id="24e79-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24e79-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24e79-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24e79-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24e79-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24e79-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24e79-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24e79-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e79-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="24e79-122">See also</span></span>

- [<span data-ttu-id="24e79-123">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="24e79-123">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="24e79-124">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="24e79-124">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
