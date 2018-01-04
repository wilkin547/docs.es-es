---
title: "ICorRuntimeHost::CreateDomainEx (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateDomainEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2a577e1bd8765c7359e521b007bea943de7a984
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="56519-102">ICorRuntimeHost::CreateDomainEx (Método)</span><span class="sxs-lookup"><span data-stu-id="56519-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="56519-103">Crea un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="56519-103">Creates an application domain.</span></span> <span data-ttu-id="56519-104">El llamador recibe un puntero de interfaz de tipo <xref:System._AppDomain>, a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="56519-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="56519-105">Este método permite al llamador pasar una instancia de IAppDomainSetup para configurar características adicionales de devuelto <xref:System._AppDomain> instancia.</span><span class="sxs-lookup"><span data-stu-id="56519-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56519-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56519-106">Syntax</span></span>  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56519-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56519-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="56519-108">[in] Un parámetro opcional que se utiliza para asignar un nombre descriptivo para el dominio.</span><span class="sxs-lookup"><span data-stu-id="56519-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="56519-109">Este nombre descriptivo puede mostrarse en las interfaces de usuario como depuradores para identificar el dominio.</span><span class="sxs-lookup"><span data-stu-id="56519-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="56519-110">[in] Un puntero de interfaz opcional de tipo `IAppDomainSetup`, obtenido mediante una llamada a la [ICorRuntimeHost:: CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="56519-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="56519-111">[in] Una matriz opcional de punteros a `IIdentity` instancias que representan la evidencia asignada mediante la directiva de seguridad para establecer un conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="56519-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="56519-112">Un `IIdentity` objeto se puede obtener mediante una llamada a la [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="56519-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="56519-113">[out] Un puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de <xref:System.AppDomain?displayProperty=nameWithType> que se puede utilizar para controlar aún más el dominio.</span><span class="sxs-lookup"><span data-stu-id="56519-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56519-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="56519-114">Return Value</span></span>  
  
|<span data-ttu-id="56519-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56519-115">HRESULT</span></span>|<span data-ttu-id="56519-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="56519-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56519-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="56519-117">S_OK</span></span>|<span data-ttu-id="56519-118">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="56519-118">The operation was successful.</span></span>|  
|<span data-ttu-id="56519-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="56519-119">S_FALSE</span></span>|<span data-ttu-id="56519-120">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="56519-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="56519-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="56519-121">E_FAIL</span></span>|<span data-ttu-id="56519-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="56519-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="56519-123">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="56519-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="56519-124">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="56519-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="56519-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="56519-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="56519-126">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="56519-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56519-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="56519-127">Remarks</span></span>  
 <span data-ttu-id="56519-128">`CreateDomainEx`amplía las capacidades de [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) al permitir que el llamador pase en un `IAppDomainSetup` instancia con valores de propiedad para configurar el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="56519-128">`CreateDomainEx` extends the capabilities of [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56519-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56519-129">Requirements</span></span>  
 <span data-ttu-id="56519-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56519-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56519-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="56519-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56519-132">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="56519-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56519-133">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="56519-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56519-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="56519-134">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 <xref:System.IAppDomainSetup?displayProperty=nameWithType>  
 [<span data-ttu-id="56519-135">CreateDomain (método)</span><span class="sxs-lookup"><span data-stu-id="56519-135">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)  
 [<span data-ttu-id="56519-136">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="56519-136">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
