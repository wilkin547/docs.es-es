---
title: ICLRRuntimeHost::GetCLRControl (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83b029c24321946f777966daa7a486f9e8e7b7a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641377"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="7d430-102">ICLRRuntimeHost::GetCLRControl (Método)</span><span class="sxs-lookup"><span data-stu-id="7d430-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="7d430-103">Obtiene un puntero de interfaz de tipo [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) que los hosts pueden usar para personalizar algunos aspectos de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7d430-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d430-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d430-104">Syntax</span></span>  
  
```  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d430-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d430-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="7d430-106">[out] Un puntero de interfaz de tipo [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) que permite a los hosts configurar aspectos adicionales de CLR.</span><span class="sxs-lookup"><span data-stu-id="7d430-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d430-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7d430-107">Return Value</span></span>  
  
|<span data-ttu-id="7d430-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d430-108">HRESULT</span></span>|<span data-ttu-id="7d430-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d430-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d430-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d430-110">S_OK</span></span>|<span data-ttu-id="7d430-111">`GetCLRControl` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7d430-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="7d430-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7d430-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7d430-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7d430-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7d430-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7d430-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7d430-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7d430-115">The call timed out.</span></span>|  
|<span data-ttu-id="7d430-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7d430-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7d430-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7d430-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7d430-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7d430-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7d430-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="7d430-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7d430-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7d430-120">E_FAIL</span></span>|<span data-ttu-id="7d430-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="7d430-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7d430-122">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="7d430-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7d430-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7d430-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7d430-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="7d430-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="7d430-125">El CLR ya ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="7d430-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d430-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d430-126">Remarks</span></span>  
 <span data-ttu-id="7d430-127">`ICLRControl` proporciona el [GetCLRManager (método)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) método, que permite que el host obtener un puntero de interfaz a uno de los tipos de administrador.</span><span class="sxs-lookup"><span data-stu-id="7d430-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d430-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d430-128">Requirements</span></span>  
 <span data-ttu-id="7d430-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d430-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d430-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7d430-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d430-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d430-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d430-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d430-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d430-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d430-133">See also</span></span>

- [<span data-ttu-id="7d430-134">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d430-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="7d430-135">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d430-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
