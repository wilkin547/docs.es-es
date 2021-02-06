---
description: 'Más información sobre: ICLRHostProtectionManager:: Setprotectedcategories ((método)'
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
ms.openlocfilehash: 9138c31ea1a2d9b7ebeaeac8ef5ef9305eabef8d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637539"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="3ecb5-103">ICLRHostProtectionManager::SetProtectedCategories (Método)</span><span class="sxs-lookup"><span data-stu-id="3ecb5-103">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>

<span data-ttu-id="3ecb5-104">Especifica qué categorías de tipos administrados y miembros deben bloquearse para que no se ejecuten en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="3ecb5-104">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ecb5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ecb5-105">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ecb5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3ecb5-106">Parameters</span></span>  

 `categories`  
 <span data-ttu-id="3ecb5-107">de Una combinación de valores de [EApiCategories](eapicategories-enumeration.md) , que indica en qué categorías de tipos y miembros administrados se debe bloquear la ejecución en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="3ecb5-107">[in] A combination of [EApiCategories](eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ecb5-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3ecb5-108">Return Value</span></span>  
  
|<span data-ttu-id="3ecb5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ecb5-109">HRESULT</span></span>|<span data-ttu-id="3ecb5-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ecb5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3ecb5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3ecb5-111">S_OK</span></span>|<span data-ttu-id="3ecb5-112">`SetProtectedCategories` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ecb5-112">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="3ecb5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3ecb5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3ecb5-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ecb5-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3ecb5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3ecb5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3ecb5-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ecb5-116">The call timed out.</span></span>|  
|<span data-ttu-id="3ecb5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ecb5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3ecb5-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3ecb5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3ecb5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3ecb5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3ecb5-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3ecb5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3ecb5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3ecb5-121">E_FAIL</span></span>|<span data-ttu-id="3ecb5-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3ecb5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3ecb5-123">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3ecb5-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3ecb5-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3ecb5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ecb5-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3ecb5-125">Remarks</span></span>  

 <span data-ttu-id="3ecb5-126">Cada `EApiCategories` valor hace referencia a una lista de miembros y tipos administrados.</span><span class="sxs-lookup"><span data-stu-id="3ecb5-126">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="3ecb5-127">La `EApiCategories` enumeración y el `SetProtectedCategories` método están directamente relacionados con la <xref:System.Security.Permissions.HostProtectionAttribute> clase administrada, que se usa para marcar los tipos administrados y los miembros que exponen las funciones correspondientes a las categorías descritas por `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="3ecb5-127">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="3ecb5-128">Para obtener más información, vea <xref:System.Security.Permissions.HostProtectionAttribute> y la <xref:System.Security.Permissions.HostProtectionResource> enumeración, que se corresponde directamente con `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="3ecb5-128">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ecb5-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ecb5-129">Requirements</span></span>  

 <span data-ttu-id="3ecb5-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ecb5-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ecb5-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3ecb5-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ecb5-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3ecb5-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ecb5-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ecb5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ecb5-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ecb5-134">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="3ecb5-135">EApiCategories (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3ecb5-135">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="3ecb5-136">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ecb5-136">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="3ecb5-137">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ecb5-137">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
