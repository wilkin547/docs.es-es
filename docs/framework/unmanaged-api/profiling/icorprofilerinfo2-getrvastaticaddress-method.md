---
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
ms.openlocfilehash: 525fa2efa39909390d874fb97d9f11e647340ea9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496950"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="40293-102">ICorProfilerInfo2::GetRVAStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="40293-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="40293-103">Obtiene la dirección del campo estático de la dirección virtual relativa (RVA) especificada.</span><span class="sxs-lookup"><span data-stu-id="40293-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40293-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40293-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40293-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40293-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="40293-106">de IDENTIFICADOR de la clase que contiene el campo de RVA-static solicitado.</span><span class="sxs-lookup"><span data-stu-id="40293-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="40293-107">de Token de metadatos para el campo de RVA-static solicitado.</span><span class="sxs-lookup"><span data-stu-id="40293-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="40293-108">enuncia Puntero a la dirección del campo de RVA-static.</span><span class="sxs-lookup"><span data-stu-id="40293-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40293-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40293-109">Remarks</span></span>  
 <span data-ttu-id="40293-110">El `GetRVAStaticAddress` método puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="40293-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="40293-111">CORPROF_E_DATAINCOMPLETE HRESULT si no se ha asignado una dirección al campo estático dado en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="40293-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="40293-112">Direcciones de los objetos que pueden estar en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="40293-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="40293-113">Estas direcciones pueden dejar de ser válidas después de la recolección de elementos no utilizados, por lo que después de la recolección de elementos no utilizados, los perfiles no deben suponer que son válidas.</span><span class="sxs-lookup"><span data-stu-id="40293-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="40293-114">Antes de que se complete el constructor de clase de una clase, `GetRVAStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE de todos sus campos estáticos, aunque es posible que algunos de los campos estáticos ya estén inicializados y puedan ser objetos de recolección de elementos no utilizados de raíz.</span><span class="sxs-lookup"><span data-stu-id="40293-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40293-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40293-115">Requirements</span></span>  
 <span data-ttu-id="40293-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40293-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40293-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40293-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40293-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40293-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40293-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40293-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40293-120">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="40293-120">See also</span></span>

- [<span data-ttu-id="40293-121">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40293-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="40293-122">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40293-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
