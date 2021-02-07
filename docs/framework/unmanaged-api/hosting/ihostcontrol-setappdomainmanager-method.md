---
description: 'Más información sobre: IHostControl:: SetAppDomainManager ((método)'
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
ms.openlocfilehash: 1fc5efc0afad73d1805338140f186a50913ca542
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708906"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="7c2dd-103">IHostControl::SetAppDomainManager (Método)</span><span class="sxs-lookup"><span data-stu-id="7c2dd-103">IHostControl::SetAppDomainManager Method</span></span>

<span data-ttu-id="7c2dd-104">Notifica al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7c2dd-104">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c2dd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c2dd-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c2dd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c2dd-106">Parameters</span></span>  

 `dwAppDomainID`  
 <span data-ttu-id="7c2dd-107">de Identificador numérico del seleccionado <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="7c2dd-107">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="7c2dd-108">de Puntero al <xref:System.AppDomainManager> objeto que el host implementa como `IUnknown` .</span><span class="sxs-lookup"><span data-stu-id="7c2dd-108">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c2dd-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7c2dd-109">Return Value</span></span>  
  
|<span data-ttu-id="7c2dd-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c2dd-110">HRESULT</span></span>|<span data-ttu-id="7c2dd-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c2dd-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c2dd-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c2dd-112">S_OK</span></span>|<span data-ttu-id="7c2dd-113">`SetAppDomainManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7c2dd-113">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="7c2dd-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c2dd-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c2dd-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7c2dd-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c2dd-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c2dd-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c2dd-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7c2dd-117">The call timed out.</span></span>|  
|<span data-ttu-id="7c2dd-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c2dd-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c2dd-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7c2dd-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c2dd-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c2dd-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c2dd-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="7c2dd-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c2dd-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c2dd-122">E_FAIL</span></span>|<span data-ttu-id="7c2dd-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="7c2dd-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c2dd-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7c2dd-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c2dd-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7c2dd-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c2dd-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7c2dd-126">Remarks</span></span>  

 <span data-ttu-id="7c2dd-127"><xref:System.AppDomainManager>Proporciona al host un mecanismo para arrancar en código administrado y controlar la creación y la configuración de cada uno de ellos <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="7c2dd-127">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="7c2dd-128"><xref:System.AppDomainManager>Se carga en cada <xref:System.AppDomain> cuando <xref:System.AppDomain> se crea.</span><span class="sxs-lookup"><span data-stu-id="7c2dd-128">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="7c2dd-129">Si elige, CLR notifica al host que el dominio de aplicación se ha creado estableciendo el valor del `pUnkAppDomainManager` parámetro.</span><span class="sxs-lookup"><span data-stu-id="7c2dd-129">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="7c2dd-130">En su implementación del `SetAppDomainManager` método, el host puede establecer el nombre y el tipo de ensamblado para el administrador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7c2dd-130">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c2dd-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c2dd-131">Requirements</span></span>  

 <span data-ttu-id="7c2dd-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c2dd-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c2dd-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7c2dd-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c2dd-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c2dd-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c2dd-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c2dd-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c2dd-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c2dd-136">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="7c2dd-137">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c2dd-137">IHostControl Interface</span></span>](ihostcontrol-interface.md)
