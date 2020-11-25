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
ms.openlocfilehash: 271f9f4fd0d85407aedf088ffb524fa6e0398e37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727216"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="53f7c-102">ICorProfilerInfo2::GetAppDomainStaticAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="53f7c-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>

<span data-ttu-id="53f7c-103">Obtiene la dirección del campo estático del dominio de aplicación especificado que está en el ámbito del dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="53f7c-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53f7c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53f7c-104">Syntax</span></span>  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53f7c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53f7c-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="53f7c-106">de IDENTIFICADOR de clase de la clase que contiene el campo estático de dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="53f7c-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="53f7c-107">de El símbolo (token) de metadatos del campo estático de dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="53f7c-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="53f7c-108">de IDENTIFICADOR del dominio de aplicación que es el ámbito del campo estático solicitado.</span><span class="sxs-lookup"><span data-stu-id="53f7c-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="53f7c-109">enuncia Puntero a la dirección del campo estático que se encuentra dentro del dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="53f7c-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53f7c-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53f7c-110">Remarks</span></span>  

 <span data-ttu-id="53f7c-111">El `GetAppDomainStaticAddress` método puede devolver uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="53f7c-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="53f7c-112">CORPROF_E_DATAINCOMPLETE HRESULT si no se ha asignado una dirección al campo estático dado en el contexto especificado.</span><span class="sxs-lookup"><span data-stu-id="53f7c-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="53f7c-113">Direcciones de los objetos que pueden estar en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="53f7c-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="53f7c-114">Estas direcciones pueden dejar de ser válidas después de la recolección de elementos no utilizados, por lo que después de la recolección de elementos no utilizados, los perfiles no deben suponer que son válidas.</span><span class="sxs-lookup"><span data-stu-id="53f7c-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="53f7c-115">Antes de que se complete el constructor de clase de una clase, `GetAppDomainStaticAddress` devolverá CORPROF_E_DATAINCOMPLETE de todos sus campos estáticos, aunque es posible que algunos de los campos estáticos ya estén inicializados y contengan objetos de recolección de elementos no utilizados de raíz.</span><span class="sxs-lookup"><span data-stu-id="53f7c-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53f7c-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53f7c-116">Requirements</span></span>  

 <span data-ttu-id="53f7c-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53f7c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53f7c-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="53f7c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="53f7c-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53f7c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53f7c-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53f7c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53f7c-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53f7c-121">See also</span></span>

- [<span data-ttu-id="53f7c-122">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="53f7c-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="53f7c-123">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="53f7c-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
