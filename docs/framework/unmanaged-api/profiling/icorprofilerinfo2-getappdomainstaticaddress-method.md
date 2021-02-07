---
description: 'Más información acerca de: ICorProfilerInfo2:: Getappdomainstaticaddress ((método)'
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
ms.openlocfilehash: 4ef8511e75a18f7626fa7a30ea194140de051bb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753242"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="2a201-103">ICorProfilerInfo2::GetAppDomainStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="2a201-103">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>

<span data-ttu-id="2a201-104">Obtiene la dirección del campo estático del dominio de aplicación especificado que está en el ámbito del dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="2a201-104">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a201-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a201-105">Syntax</span></span>  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a201-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a201-106">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="2a201-107">de IDENTIFICADOR de clase de la clase que contiene el campo estático de dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="2a201-107">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="2a201-108">de El símbolo (token) de metadatos del campo estático de dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="2a201-108">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="2a201-109">de IDENTIFICADOR del dominio de aplicación que es el ámbito del campo estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="2a201-109">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="2a201-110">enuncia Puntero a la dirección del campo estático que se encuentra dentro del dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="2a201-110">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a201-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2a201-111">Remarks</span></span>  

 <span data-ttu-id="2a201-112">El `GetAppDomainStaticAddress` método puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2a201-112">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="2a201-113">CORPROF_E_DATAINCOMPLETE HRESULT si no se ha asignado una dirección al campo estático dado en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="2a201-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="2a201-114">Direcciones de los objetos que pueden estar en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2a201-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="2a201-115">Estas direcciones pueden dejar de ser válidas después de la recolección de elementos no utilizados, por lo que después de la recolección de elementos no utilizados, los perfiles no deben suponer que son válidas.</span><span class="sxs-lookup"><span data-stu-id="2a201-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="2a201-116">Antes de que se complete el constructor de clase de una clase, `GetAppDomainStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE de todos sus campos estáticos, aunque es posible que algunos de los campos estáticos ya estén inicializados y contengan objetos de recolección de elementos no utilizados de raíz.</span><span class="sxs-lookup"><span data-stu-id="2a201-116">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a201-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a201-117">Requirements</span></span>  

 <span data-ttu-id="2a201-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a201-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a201-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2a201-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2a201-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a201-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a201-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a201-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a201-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a201-122">See also</span></span>

- [<span data-ttu-id="2a201-123">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a201-123">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="2a201-124">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a201-124">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
