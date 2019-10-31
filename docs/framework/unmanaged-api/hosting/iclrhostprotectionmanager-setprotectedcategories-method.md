---
title: ICLRHostProtectionManager::SetProtectedCategories (Método)
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
ms.openlocfilehash: e3f2429462b4454e87690d98ad9fb446574add91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141041"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="94686-102">ICLRHostProtectionManager::SetProtectedCategories (Método)</span><span class="sxs-lookup"><span data-stu-id="94686-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="94686-103">Especifica qué categorías de tipos administrados y miembros deben bloquearse para que no se ejecuten en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="94686-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94686-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94686-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94686-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94686-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="94686-106">de Una combinación de valores de [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) , que indica en qué categorías de tipos y miembros administrados se debe bloquear la ejecución en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="94686-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94686-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="94686-107">Return Value</span></span>  
  
|<span data-ttu-id="94686-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94686-108">HRESULT</span></span>|<span data-ttu-id="94686-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="94686-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94686-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="94686-110">S_OK</span></span>|<span data-ttu-id="94686-111">`SetProtectedCategories` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="94686-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="94686-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="94686-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="94686-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="94686-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="94686-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="94686-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="94686-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="94686-115">The call timed out.</span></span>|  
|<span data-ttu-id="94686-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="94686-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="94686-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="94686-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="94686-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="94686-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="94686-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="94686-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="94686-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94686-120">E_FAIL</span></span>|<span data-ttu-id="94686-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="94686-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="94686-122">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="94686-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="94686-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="94686-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94686-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94686-124">Remarks</span></span>  
 <span data-ttu-id="94686-125">Cada valor de `EApiCategories` hace referencia a una lista de miembros y tipos administrados.</span><span class="sxs-lookup"><span data-stu-id="94686-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="94686-126">La enumeración `EApiCategories` y el método `SetProtectedCategories` se relacionan directamente con la clase <xref:System.Security.Permissions.HostProtectionAttribute> administrada, que se usa para marcar los tipos administrados y los miembros que exponen las funciones correspondientes a las categorías descritas por `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="94686-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="94686-127">Para obtener más información, vea <xref:System.Security.Permissions.HostProtectionAttribute> y la enumeración <xref:System.Security.Permissions.HostProtectionResource>, que se corresponde directamente con `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="94686-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94686-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94686-128">Requirements</span></span>  
 <span data-ttu-id="94686-129">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94686-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94686-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="94686-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94686-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="94686-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94686-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94686-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94686-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="94686-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="94686-134">EApiCategories (enumeración)</span><span class="sxs-lookup"><span data-stu-id="94686-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="94686-135">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="94686-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="94686-136">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="94686-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
