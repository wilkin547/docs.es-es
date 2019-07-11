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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03c969cbda8fdaf8fa418c2246f3d0937e622250
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765746"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="5e13b-102">ICLRRuntimeHost::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="5e13b-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="5e13b-103">Inicializa common language runtime (CLR) en un proceso.</span><span class="sxs-lookup"><span data-stu-id="5e13b-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e13b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e13b-104">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5e13b-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5e13b-105">Return Value</span></span>  
  
|<span data-ttu-id="5e13b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e13b-106">HRESULT</span></span>|<span data-ttu-id="5e13b-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5e13b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e13b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e13b-108">S_OK</span></span>|<span data-ttu-id="5e13b-109">`Start` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5e13b-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="5e13b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e13b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e13b-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5e13b-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e13b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e13b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e13b-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="5e13b-113">The call timed out.</span></span>|  
|<span data-ttu-id="5e13b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e13b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e13b-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5e13b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e13b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e13b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e13b-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="5e13b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e13b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e13b-118">E_FAIL</span></span>|<span data-ttu-id="5e13b-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="5e13b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e13b-120">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="5e13b-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e13b-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5e13b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e13b-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e13b-122">Remarks</span></span>  
 <span data-ttu-id="5e13b-123">En muchos escenarios no es necesario llamar a `Start`, ya que el tiempo de ejecución se inicializará automáticamente tras la primera solicitud para ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="5e13b-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="5e13b-124">Sin embargo, puede usar `Start` para especificar exactamente cuándo el tiempo de ejecución debe llevarse a cabo.</span><span class="sxs-lookup"><span data-stu-id="5e13b-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e13b-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e13b-125">Requirements</span></span>  
 <span data-ttu-id="5e13b-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e13b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e13b-127">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5e13b-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e13b-128">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5e13b-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e13b-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e13b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e13b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e13b-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="5e13b-131">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e13b-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
