---
title: ICorProfilerCallback::AppDomainCreationFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
ms.openlocfilehash: 76f56971223154d3ed966c272081049adf30de54
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500499"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="ee734-102">ICorProfilerCallback::AppDomainCreationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="ee734-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="ee734-103">Notifica al generador de perfiles que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ee734-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee734-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee734-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a><span data-ttu-id="ee734-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ee734-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="ee734-106">\[en] identifica el dominio que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="ee734-106">\[in] Identifies the domain which has been created.</span></span>

- `hrStatus`

  <span data-ttu-id="ee734-107">\[in] un valor HRESULT que indica si la creación del dominio de aplicación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ee734-107">\[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee734-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ee734-108">Remarks</span></span>  
 <span data-ttu-id="ee734-109">El ID. de aplicación no es válido para ninguna solicitud de información hasta que `AppDomainCreationFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="ee734-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="ee734-110">Algunas partes de la carga del dominio de aplicación pueden continuar después de la `AppDomainCreationFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="ee734-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="ee734-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="ee734-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="ee734-112">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la creación del dominio de aplicación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="ee734-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee734-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee734-113">Requirements</span></span>  
 <span data-ttu-id="ee734-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee734-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee734-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ee734-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ee734-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee734-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee734-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee734-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee734-118">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="ee734-118">See also</span></span>

- [<span data-ttu-id="ee734-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee734-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
