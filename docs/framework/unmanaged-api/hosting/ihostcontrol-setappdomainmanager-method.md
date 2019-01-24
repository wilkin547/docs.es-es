---
title: IHostControl::SetAppDomainManager (Método)
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fd0cf4f47781afb397c1fdd4b42715c710982e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580764"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="4a6ed-102">IHostControl::SetAppDomainManager (Método)</span><span class="sxs-lookup"><span data-stu-id="4a6ed-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="4a6ed-103">Notifica al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a6ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a6ed-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a6ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4a6ed-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="4a6ed-106">[in] El identificador numérico del seleccionado <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="4a6ed-107">[in] Un puntero a la <xref:System.AppDomainManager> objeto que implementa el host como `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a6ed-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4a6ed-108">Return Value</span></span>  
  
|<span data-ttu-id="4a6ed-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a6ed-109">HRESULT</span></span>|<span data-ttu-id="4a6ed-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a6ed-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a6ed-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a6ed-111">S_OK</span></span>|<span data-ttu-id="4a6ed-112">`SetAppDomainManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="4a6ed-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a6ed-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a6ed-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a6ed-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a6ed-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a6ed-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-116">The call timed out.</span></span>|  
|<span data-ttu-id="4a6ed-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a6ed-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a6ed-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a6ed-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a6ed-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a6ed-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a6ed-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a6ed-121">E_FAIL</span></span>|<span data-ttu-id="4a6ed-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a6ed-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a6ed-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a6ed-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a6ed-125">Remarks</span></span>  
 <span data-ttu-id="4a6ed-126">El <xref:System.AppDomainManager> proporciona el host con un mecanismo para arrancar en código administrado y controlar la creación y configuración de cada <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="4a6ed-127">El <xref:System.AppDomainManager> se carga en cada uno de ellos <xref:System.AppDomain> cuando que <xref:System.AppDomain> se crea.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="4a6ed-128">Si lo elige, CLR notifica al host que se ha creado el dominio de aplicación estableciendo el valor de la `pUnkAppDomainManager` parámetro.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="4a6ed-129">En su implementación de la `SetAppDomainManager` método, el host puede establecer el nombre de ensamblado y tipo para el Administrador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a6ed-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a6ed-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a6ed-130">Requirements</span></span>  
 <span data-ttu-id="4a6ed-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a6ed-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a6ed-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4a6ed-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a6ed-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4a6ed-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a6ed-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a6ed-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6ed-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a6ed-135">See also</span></span>
- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="4a6ed-136">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a6ed-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
