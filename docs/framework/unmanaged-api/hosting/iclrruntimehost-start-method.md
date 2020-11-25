---
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
ms.openlocfilehash: 2358af3dff97dbe648da924bc929dd2f83b12df0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728815"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="38619-102">ICLRRuntimeHost::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="38619-102">ICLRRuntimeHost::Start Method</span></span>

<span data-ttu-id="38619-103">Inicializa el Common Language Runtime (CLR) en un proceso.</span><span class="sxs-lookup"><span data-stu-id="38619-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38619-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38619-104">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="38619-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="38619-105">Return Value</span></span>  
  
|<span data-ttu-id="38619-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="38619-106">HRESULT</span></span>|<span data-ttu-id="38619-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="38619-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="38619-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="38619-108">S_OK</span></span>|<span data-ttu-id="38619-109">`Start` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="38619-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="38619-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="38619-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="38619-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="38619-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="38619-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="38619-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="38619-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="38619-113">The call timed out.</span></span>|  
|<span data-ttu-id="38619-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="38619-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="38619-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="38619-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="38619-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="38619-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="38619-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="38619-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="38619-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="38619-118">E_FAIL</span></span>|<span data-ttu-id="38619-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="38619-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="38619-120">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="38619-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="38619-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="38619-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38619-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38619-122">Remarks</span></span>  

 <span data-ttu-id="38619-123">En muchos escenarios no es necesario llamar a `Start` , porque el tiempo de ejecución se inicializará automáticamente en la primera solicitud para ejecutar el código administrado.</span><span class="sxs-lookup"><span data-stu-id="38619-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="38619-124">Sin embargo, puede usar `Start` para especificar exactamente cuándo se debe inicializar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="38619-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38619-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38619-125">Requirements</span></span>  

 <span data-ttu-id="38619-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38619-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38619-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="38619-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38619-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38619-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38619-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38619-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38619-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="38619-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="38619-131">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="38619-131">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
