---
description: 'Más información sobre: ICLRRuntimeHost:: Start (método)'
title: ICLRRuntimeHost::Start (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type:
- apiref
ms.openlocfilehash: 0ada729c9a90b23fb1573a2101845028e5e2fe76
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785086"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="73224-103">ICLRRuntimeHost::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="73224-103">ICLRRuntimeHost::Start Method</span></span>

<span data-ttu-id="73224-104">Inicializa el Common Language Runtime (CLR) en un proceso.</span><span class="sxs-lookup"><span data-stu-id="73224-104">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73224-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73224-105">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="73224-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="73224-106">Return Value</span></span>  
  
|<span data-ttu-id="73224-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73224-107">HRESULT</span></span>|<span data-ttu-id="73224-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="73224-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73224-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="73224-109">S_OK</span></span>|<span data-ttu-id="73224-110">`Start` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="73224-110">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="73224-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="73224-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="73224-112">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="73224-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="73224-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="73224-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="73224-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="73224-114">The call timed out.</span></span>|  
|<span data-ttu-id="73224-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="73224-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="73224-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="73224-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="73224-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="73224-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="73224-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="73224-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="73224-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="73224-119">E_FAIL</span></span>|<span data-ttu-id="73224-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="73224-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="73224-121">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="73224-121">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="73224-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="73224-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73224-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="73224-123">Remarks</span></span>  

 <span data-ttu-id="73224-124">En muchos escenarios no es necesario llamar a `Start` , porque el tiempo de ejecución se inicializará automáticamente en la primera solicitud para ejecutar el código administrado.</span><span class="sxs-lookup"><span data-stu-id="73224-124">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="73224-125">Sin embargo, puede usar `Start` para especificar exactamente cuándo se debe inicializar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="73224-125">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73224-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73224-126">Requirements</span></span>  

 <span data-ttu-id="73224-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73224-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73224-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="73224-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73224-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73224-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73224-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73224-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73224-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="73224-131">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="73224-132">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="73224-132">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
