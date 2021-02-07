---
description: 'Más información acerca de: ICorProfilerInfo2:: GetRVAStaticAddress ((método)'
title: ICorProfilerInfo2::GetRVAStaticAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
ms.openlocfilehash: e72a136ca0d8462d19c57da021e9429528555dac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716411"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="2c3ff-103">ICorProfilerInfo2::GetRVAStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="2c3ff-103">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>

<span data-ttu-id="2c3ff-104">Obtiene la dirección del campo estático de la dirección virtual relativa (RVA) especificada.</span><span class="sxs-lookup"><span data-stu-id="2c3ff-104">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c3ff-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c3ff-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c3ff-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c3ff-106">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="2c3ff-107">de IDENTIFICADOR de la clase que contiene el campo de RVA-static solicitado.</span><span class="sxs-lookup"><span data-stu-id="2c3ff-107">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="2c3ff-108">de Token de metadatos para el campo de RVA-static solicitado.</span><span class="sxs-lookup"><span data-stu-id="2c3ff-108">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="2c3ff-109">enuncia Puntero a la dirección del campo de RVA-static.</span><span class="sxs-lookup"><span data-stu-id="2c3ff-109">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c3ff-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2c3ff-110">Remarks</span></span>  

 <span data-ttu-id="2c3ff-111">El `GetRVAStaticAddress` método puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2c3ff-111">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="2c3ff-112">CORPROF_E_DATAINCOMPLETE HRESULT si no se ha asignado una dirección al campo estático dado en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="2c3ff-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="2c3ff-113">Direcciones de los objetos que pueden estar en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2c3ff-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="2c3ff-114">Estas direcciones pueden dejar de ser válidas después de la recolección de elementos no utilizados, por lo que después de la recolección de elementos no utilizados, los perfiles no deben suponer que son válidas.</span><span class="sxs-lookup"><span data-stu-id="2c3ff-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="2c3ff-115">Antes de que se complete el constructor de clase de una clase, `GetRVAStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE de todos sus campos estáticos, aunque es posible que algunos de los campos estáticos ya estén inicializados y puedan ser objetos de recolección de elementos no utilizados de raíz.</span><span class="sxs-lookup"><span data-stu-id="2c3ff-115">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c3ff-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c3ff-116">Requirements</span></span>  

 <span data-ttu-id="2c3ff-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c3ff-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c3ff-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2c3ff-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2c3ff-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c3ff-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c3ff-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c3ff-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c3ff-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c3ff-121">See also</span></span>

- [<span data-ttu-id="2c3ff-122">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c3ff-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="2c3ff-123">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c3ff-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
