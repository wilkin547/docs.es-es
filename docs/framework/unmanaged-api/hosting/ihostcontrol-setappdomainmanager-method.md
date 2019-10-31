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
ms.openlocfilehash: de264135450190fd028eb8cf12017d94cc65ffac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134723"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="fd576-102">IHostControl::SetAppDomainManager (Método)</span><span class="sxs-lookup"><span data-stu-id="fd576-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="fd576-103">Notifica al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd576-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd576-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd576-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd576-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd576-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="fd576-106">de Identificador numérico de la <xref:System.AppDomain>seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fd576-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="fd576-107">de Puntero al objeto <xref:System.AppDomainManager> que el host implementa como `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="fd576-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd576-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fd576-108">Return Value</span></span>  
  
|<span data-ttu-id="fd576-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd576-109">HRESULT</span></span>|<span data-ttu-id="fd576-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd576-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd576-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd576-111">S_OK</span></span>|<span data-ttu-id="fd576-112">`SetAppDomainManager` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fd576-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="fd576-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd576-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd576-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="fd576-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fd576-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fd576-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fd576-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="fd576-116">The call timed out.</span></span>|  
|<span data-ttu-id="fd576-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fd576-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fd576-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fd576-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fd576-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fd576-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fd576-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="fd576-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fd576-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd576-121">E_FAIL</span></span>|<span data-ttu-id="fd576-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="fd576-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fd576-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="fd576-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fd576-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fd576-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd576-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd576-125">Remarks</span></span>  
 <span data-ttu-id="fd576-126">El <xref:System.AppDomainManager> proporciona al host un mecanismo para arrancar en código administrado y controlar la creación y la configuración de cada <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="fd576-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="fd576-127">El <xref:System.AppDomainManager> se carga en cada <xref:System.AppDomain> cuando se crea ese <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="fd576-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="fd576-128">Si elige, CLR notifica al host que el dominio de aplicación se ha creado estableciendo el valor del parámetro `pUnkAppDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="fd576-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="fd576-129">En su implementación del método `SetAppDomainManager`, el host puede establecer el nombre y el tipo del ensamblado para el administrador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd576-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd576-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd576-130">Requirements</span></span>  
 <span data-ttu-id="fd576-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd576-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd576-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fd576-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd576-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fd576-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd576-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd576-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd576-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd576-135">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="fd576-136">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd576-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
