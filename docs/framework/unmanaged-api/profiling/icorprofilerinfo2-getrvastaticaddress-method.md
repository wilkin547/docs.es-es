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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d3749c600d54671071efbec8322e050cde446c27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158618"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="0b618-102">ICorProfilerInfo2::GetRVAStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="0b618-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="0b618-103">Obtiene la dirección del campo estático de dirección virtual relativa (RVA) especificado.</span><span class="sxs-lookup"><span data-stu-id="0b618-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b618-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b618-104">Syntax</span></span>  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b618-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0b618-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="0b618-106">[in] El identificador de la clase que contiene el campo estático de RVA solicitado.</span><span class="sxs-lookup"><span data-stu-id="0b618-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="0b618-107">[in] Token de metadatos para el campo estático adresa RVA solicitado.</span><span class="sxs-lookup"><span data-stu-id="0b618-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="0b618-108">[out] Un puntero a la dirección del campo estático adresa RVA.</span><span class="sxs-lookup"><span data-stu-id="0b618-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b618-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b618-109">Remarks</span></span>  
 <span data-ttu-id="0b618-110">El `GetRVAStaticAddress` método puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0b618-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="0b618-111">Un HRESULT CORPROF_E_DATAINCOMPLETE si el campo estático especificado no se ha asignado una dirección en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="0b618-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="0b618-112">Las direcciones de los objetos que pueden estar en el montón de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0b618-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="0b618-113">Estas direcciones pueden no ser válidas después de la recolección de elementos, por lo que después de la recolección de elementos, los generadores de perfiles no deben suponer que son válidos.</span><span class="sxs-lookup"><span data-stu-id="0b618-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="0b618-114">Antes de que se complete el constructor de clase de una clase, `GetRVAStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque algunos de los campos estáticos pueden estar ya inicializados y pueden ser a animar a los objetos de colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0b618-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b618-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b618-115">Requirements</span></span>  
 <span data-ttu-id="0b618-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b618-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b618-117">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0b618-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0b618-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b618-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0b618-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0b618-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0b618-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b618-120">See also</span></span>

- [<span data-ttu-id="0b618-121">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b618-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="0b618-122">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b618-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
