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
ms.openlocfilehash: 2f4c004db39c14e7a71b0caa55a6089e8f69ca3a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680667"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="6d764-102">IHostControl::SetAppDomainManager (Método)</span><span class="sxs-lookup"><span data-stu-id="6d764-102">IHostControl::SetAppDomainManager Method</span></span>

<span data-ttu-id="6d764-103">Notifica al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6d764-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d764-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d764-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d764-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d764-105">Parameters</span></span>  

 `dwAppDomainID`  
 <span data-ttu-id="6d764-106">de Identificador numérico del seleccionado <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="6d764-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="6d764-107">de Puntero al <xref:System.AppDomainManager> objeto que el host implementa como `IUnknown` .</span><span class="sxs-lookup"><span data-stu-id="6d764-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d764-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6d764-108">Return Value</span></span>  
  
|<span data-ttu-id="6d764-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d764-109">HRESULT</span></span>|<span data-ttu-id="6d764-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d764-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d764-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d764-111">S_OK</span></span>|<span data-ttu-id="6d764-112">`SetAppDomainManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6d764-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="6d764-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6d764-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6d764-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6d764-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6d764-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6d764-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6d764-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6d764-116">The call timed out.</span></span>|  
|<span data-ttu-id="6d764-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6d764-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6d764-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6d764-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6d764-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6d764-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6d764-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="6d764-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6d764-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6d764-121">E_FAIL</span></span>|<span data-ttu-id="6d764-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="6d764-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6d764-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="6d764-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6d764-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6d764-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d764-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d764-125">Remarks</span></span>  

 <span data-ttu-id="6d764-126"><xref:System.AppDomainManager>Proporciona al host un mecanismo para arrancar en código administrado y controlar la creación y la configuración de cada uno de ellos <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="6d764-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="6d764-127"><xref:System.AppDomainManager>Se carga en cada <xref:System.AppDomain> cuando <xref:System.AppDomain> se crea.</span><span class="sxs-lookup"><span data-stu-id="6d764-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="6d764-128">Si elige, CLR notifica al host que el dominio de aplicación se ha creado estableciendo el valor del `pUnkAppDomainManager` parámetro.</span><span class="sxs-lookup"><span data-stu-id="6d764-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="6d764-129">En su implementación del `SetAppDomainManager` método, el host puede establecer el nombre y el tipo de ensamblado para el administrador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6d764-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d764-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d764-130">Requirements</span></span>  

 <span data-ttu-id="6d764-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d764-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d764-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6d764-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d764-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d764-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d764-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d764-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d764-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d764-135">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="6d764-136">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d764-136">IHostControl Interface</span></span>](ihostcontrol-interface.md)
