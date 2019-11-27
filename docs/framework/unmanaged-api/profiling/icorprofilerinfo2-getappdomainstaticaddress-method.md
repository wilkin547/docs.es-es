---
title: ICorProfilerInfo2::GetAppDomainStaticAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
ms.openlocfilehash: 12c9b30dc72d1ccf7bfa79ca0745ba3f2c2290c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435876"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="65fef-102">ICorProfilerInfo2::GetAppDomainStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="65fef-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="65fef-103">Obtiene la dirección del campo estático del dominio de aplicación especificado que está en el ámbito del dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="65fef-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65fef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65fef-104">Syntax</span></span>  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65fef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="65fef-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="65fef-106">de IDENTIFICADOR de clase de la clase que contiene el campo estático de dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="65fef-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="65fef-107">de El símbolo (token) de metadatos del campo estático de dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="65fef-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="65fef-108">de IDENTIFICADOR del dominio de aplicación que es el ámbito del campo estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="65fef-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="65fef-109">enuncia Puntero a la dirección del campo estático que se encuentra dentro del dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="65fef-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65fef-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="65fef-110">Remarks</span></span>  
 <span data-ttu-id="65fef-111">El método `GetAppDomainStaticAddress` puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="65fef-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="65fef-112">CORPROF_E_DATAINCOMPLETE HRESULT si no se ha asignado una dirección al campo estático dado en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="65fef-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="65fef-113">Direcciones de los objetos que pueden estar en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="65fef-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="65fef-114">Estas direcciones pueden dejar de ser válidas después de la recolección de elementos no utilizados, por lo que después de la recolección de elementos no utilizados, los perfiles no deben suponer que son válidas.</span><span class="sxs-lookup"><span data-stu-id="65fef-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="65fef-115">Antes de que se complete el constructor de clase de una clase, `GetAppDomainStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque es posible que algunos de los campos estáticos ya estén inicializados y contengan objetos de recolección de elementos no utilizados de raíz.</span><span class="sxs-lookup"><span data-stu-id="65fef-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65fef-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65fef-116">Requirements</span></span>  
 <span data-ttu-id="65fef-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65fef-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65fef-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="65fef-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="65fef-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65fef-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65fef-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65fef-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65fef-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="65fef-121">See also</span></span>

- [<span data-ttu-id="65fef-122">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="65fef-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="65fef-123">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="65fef-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
