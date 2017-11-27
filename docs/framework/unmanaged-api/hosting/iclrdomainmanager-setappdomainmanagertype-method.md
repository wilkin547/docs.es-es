---
title: "ICLRDomainManager::SetAppDomainManagerType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager.SetAppDomainManagerType
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 17c99d21155d8f985ea455e171067855edcafedc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="17de4-102">ICLRDomainManager::SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="17de4-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="17de4-103">Especifica el tipo, derivado de la <xref:System.AppDomainManager?displayProperty=nameWithType> (clase), del Administrador de dominio de aplicación que se usarán para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="17de4-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17de4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17de4-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17de4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="17de4-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="17de4-106">[in] El nombre para mostrar del ensamblado que contiene el tipo de administrador de dominio de aplicación; Por ejemplo: "AdMgrExample, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf150f00b3".</span><span class="sxs-lookup"><span data-stu-id="17de4-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="17de4-107">[in] El nombre de tipo de administrador de dominio de aplicación, incluido el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="17de4-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="17de4-108">[in] Una combinación de [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) valores de enumeración que proporcionan información acerca del Administrador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="17de4-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17de4-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="17de4-109">Return Value</span></span>  
 <span data-ttu-id="17de4-110">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="17de4-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="17de4-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="17de4-111">HRESULT</span></span>|<span data-ttu-id="17de4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="17de4-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17de4-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="17de4-113">S_OK</span></span>|<span data-ttu-id="17de4-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="17de4-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="17de4-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="17de4-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="17de4-116">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="17de4-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17de4-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17de4-117">Remarks</span></span>  
 <span data-ttu-id="17de4-118">Actualmente, el único valor definido por el de `dwInitializeDomainFlags` es `eInitializeNewDomainFlags_NoSecurityChanges`, lo que indica que common language runtime (CLR) que el Administrador de dominio de aplicación no modificará la configuración de seguridad durante la ejecución de la <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="17de4-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="17de4-119">Esto permite que el CLR optimizar la carga de ensamblados que tienen el atributo conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo (APTCA).</span><span class="sxs-lookup"><span data-stu-id="17de4-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="17de4-120">Esto puede producir una mejora significativa en tiempo de inicio si el cierre transitivo de este conjunto de ensamblados es grande.</span><span class="sxs-lookup"><span data-stu-id="17de4-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="17de4-121">Si el host especifica `eInitializeNewDomainFlags_NoSecurityChanges` para el Administrador de dominio de aplicación, un <xref:System.InvalidOperationException> se produce si intenta modificar la seguridad del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="17de4-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="17de4-122">Llamar a la [ICLRControl:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)es equivalente a llamar al método `ICLRDomainManager::SetAppDomainManagerType` con `eInitializeNewDomainFlags_None`.</span><span class="sxs-lookup"><span data-stu-id="17de4-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17de4-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17de4-123">Requirements</span></span>  
 <span data-ttu-id="17de4-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17de4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17de4-125">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="17de4-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="17de4-126">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="17de4-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17de4-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17de4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17de4-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="17de4-128">See Also</span></span>  
 [<span data-ttu-id="17de4-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="17de4-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="17de4-130">ICLRDomainManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="17de4-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 [<span data-ttu-id="17de4-131">EInitializeNewDomainFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="17de4-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
