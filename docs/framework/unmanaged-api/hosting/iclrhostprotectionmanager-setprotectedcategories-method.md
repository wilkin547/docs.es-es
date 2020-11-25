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
ms.openlocfilehash: 0557a8f1c7c495950933a44cacd23ada8e84964e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730505"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="724d6-102">ICLRHostProtectionManager::SetProtectedCategories (Método)</span><span class="sxs-lookup"><span data-stu-id="724d6-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>

<span data-ttu-id="724d6-103">Especifica qué categorías de tipos administrados y miembros deben bloquearse para que no se ejecuten en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="724d6-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="724d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="724d6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="724d6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="724d6-105">Parameters</span></span>  

 `categories`  
 <span data-ttu-id="724d6-106">de Una combinación de valores de [EApiCategories](eapicategories-enumeration.md) , que indica en qué categorías de tipos y miembros administrados se debe bloquear la ejecución en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="724d6-106">[in] A combination of [EApiCategories](eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="724d6-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="724d6-107">Return Value</span></span>  
  
|<span data-ttu-id="724d6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="724d6-108">HRESULT</span></span>|<span data-ttu-id="724d6-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="724d6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="724d6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="724d6-110">S_OK</span></span>|<span data-ttu-id="724d6-111">`SetProtectedCategories` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="724d6-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="724d6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="724d6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="724d6-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="724d6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="724d6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="724d6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="724d6-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="724d6-115">The call timed out.</span></span>|  
|<span data-ttu-id="724d6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="724d6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="724d6-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="724d6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="724d6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="724d6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="724d6-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="724d6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="724d6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="724d6-120">E_FAIL</span></span>|<span data-ttu-id="724d6-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="724d6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="724d6-122">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="724d6-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="724d6-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="724d6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="724d6-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="724d6-124">Remarks</span></span>  

 <span data-ttu-id="724d6-125">Cada `EApiCategories` valor hace referencia a una lista de miembros y tipos administrados.</span><span class="sxs-lookup"><span data-stu-id="724d6-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="724d6-126">La `EApiCategories` enumeración y el `SetProtectedCategories` método están directamente relacionados con la <xref:System.Security.Permissions.HostProtectionAttribute> clase administrada, que se usa para marcar los tipos administrados y los miembros que exponen las funciones correspondientes a las categorías descritas por `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="724d6-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="724d6-127">Para obtener más información, vea <xref:System.Security.Permissions.HostProtectionAttribute> y la <xref:System.Security.Permissions.HostProtectionResource> enumeración, que se corresponde directamente con `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="724d6-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="724d6-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="724d6-128">Requirements</span></span>  

 <span data-ttu-id="724d6-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="724d6-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="724d6-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="724d6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="724d6-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="724d6-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="724d6-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="724d6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="724d6-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="724d6-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="724d6-134">EApiCategories (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="724d6-134">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="724d6-135">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="724d6-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="724d6-136">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="724d6-136">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
