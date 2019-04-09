---
title: ICorRuntimeHost::CreateDomainEx (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a538f14e7dbf24a94343f364201e968bffa757f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158930"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="d973e-102">ICorRuntimeHost::CreateDomainEx (Método)</span><span class="sxs-lookup"><span data-stu-id="d973e-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="d973e-103">Crea un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d973e-103">Creates an application domain.</span></span> <span data-ttu-id="d973e-104">El llamador recibe un puntero de interfaz de tipo <xref:System._AppDomain>, a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d973e-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d973e-105">Este método permite al llamador pasar una instancia de IAppDomainSetup para configurar características adicionales de devuelto <xref:System._AppDomain> instancia.</span><span class="sxs-lookup"><span data-stu-id="d973e-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d973e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d973e-106">Syntax</span></span>  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d973e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d973e-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="d973e-108">[in] Un parámetro opcional que se utiliza para asignar un nombre descriptivo para el dominio.</span><span class="sxs-lookup"><span data-stu-id="d973e-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="d973e-109">Este nombre descriptivo puede mostrarse en las interfaces de usuario, como los depuradores para identificar el dominio.</span><span class="sxs-lookup"><span data-stu-id="d973e-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="d973e-110">[in] Un puntero de interfaz opcional de tipo `IAppDomainSetup`, obtenida por una llamada a la [CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d973e-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="d973e-111">[in] Una matriz opcional de punteros a `IIdentity` instancias que representan la evidencia asignada mediante la directiva de seguridad para establecer un conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="d973e-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="d973e-112">Un `IIdentity` puede obtenerse un objeto mediante una llamada a la [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d973e-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="d973e-113">[out] Un puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de <xref:System.AppDomain?displayProperty=nameWithType> que puede utilizarse para controlar aún más el dominio.</span><span class="sxs-lookup"><span data-stu-id="d973e-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d973e-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d973e-114">Return Value</span></span>  
  
|<span data-ttu-id="d973e-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d973e-115">HRESULT</span></span>|<span data-ttu-id="d973e-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="d973e-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d973e-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="d973e-117">S_OK</span></span>|<span data-ttu-id="d973e-118">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="d973e-118">The operation was successful.</span></span>|  
|<span data-ttu-id="d973e-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d973e-119">S_FALSE</span></span>|<span data-ttu-id="d973e-120">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="d973e-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="d973e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d973e-121">E_FAIL</span></span>|<span data-ttu-id="d973e-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="d973e-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="d973e-123">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d973e-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="d973e-124">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d973e-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d973e-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d973e-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d973e-126">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d973e-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d973e-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d973e-127">Remarks</span></span>  
 `CreateDomainEx` <span data-ttu-id="d973e-128">amplía las capacidades de [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) permitiendo que el llamador pase un `IAppDomainSetup` instancia con valores de propiedad para configurar el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d973e-128">extends the capabilities of [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d973e-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d973e-129">Requirements</span></span>  
 <span data-ttu-id="d973e-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d973e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d973e-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d973e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d973e-132">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d973e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d973e-133">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="d973e-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d973e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="d973e-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="d973e-135">Método CreateDomain</span><span class="sxs-lookup"><span data-stu-id="d973e-135">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="d973e-136">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d973e-136">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
