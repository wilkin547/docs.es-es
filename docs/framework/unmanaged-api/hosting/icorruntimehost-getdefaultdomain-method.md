---
title: ICorRuntimeHost::GetDefaultDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2351fbb26a38f408d330db3f7600120bd57d6e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437887"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="5242a-102">ICorRuntimeHost::GetDefaultDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="5242a-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="5242a-103">Obtiene un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> que representa el dominio predeterminado para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="5242a-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5242a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5242a-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5242a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5242a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5242a-106">[out] Un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> a la <xref:System.AppDomain> instancia que representa el dominio de aplicación predeterminado para el proceso.</span><span class="sxs-lookup"><span data-stu-id="5242a-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="5242a-107">Este puntero es de tipo `IUnknown`, por lo que los llamadores generalmente deben llamar a `QueryInterface` para obtener un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5242a-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5242a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5242a-108">Return Value</span></span>  
  
|<span data-ttu-id="5242a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5242a-109">HRESULT</span></span>|<span data-ttu-id="5242a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5242a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5242a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5242a-111">S_OK</span></span>|<span data-ttu-id="5242a-112">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="5242a-112">The operation was successful.</span></span>|  
|<span data-ttu-id="5242a-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5242a-113">S_FALSE</span></span>|<span data-ttu-id="5242a-114">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="5242a-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="5242a-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5242a-115">E_FAIL</span></span>|<span data-ttu-id="5242a-116">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="5242a-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="5242a-117">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5242a-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="5242a-118">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5242a-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5242a-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5242a-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5242a-120">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5242a-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5242a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5242a-121">Requirements</span></span>  
 <span data-ttu-id="5242a-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5242a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5242a-123">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5242a-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5242a-124">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5242a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5242a-125">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="5242a-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5242a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5242a-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="5242a-127">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5242a-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
