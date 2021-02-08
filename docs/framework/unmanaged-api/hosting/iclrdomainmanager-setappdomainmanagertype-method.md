---
description: 'Más información sobre: ICLRDomainManager:: Setappdomainmanagertype ((método)'
title: ICLRDomainManager::SetAppDomainManagerType (Método)
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
ms.openlocfilehash: 479e6596982d21c4e9ae445a7d4453235dbef729
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799764"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="29c33-103">ICLRDomainManager::SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="29c33-103">ICLRDomainManager::SetAppDomainManagerType Method</span></span>

<span data-ttu-id="29c33-104">Especifica el tipo, derivado de la <xref:System.AppDomainManager?displayProperty=nameWithType> clase, del administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="29c33-104">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29c33-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29c33-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29c33-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="29c33-106">Parameters</span></span>  

 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="29c33-107">de El nombre para mostrar del ensamblado que contiene el tipo de administrador de dominio de aplicación; por ejemplo: "AdMgrExample, version = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf150f00b3".</span><span class="sxs-lookup"><span data-stu-id="29c33-107">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="29c33-108">de El nombre de tipo del administrador del dominio de aplicación, incluido el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="29c33-108">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="29c33-109">de Combinación de valores de enumeración de [einitializenewdomainflags (](einitializenewdomainflags-enumeration.md) que proporcionan información sobre el administrador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29c33-109">[in] A combination of [EInitializeNewDomainFlags](einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29c33-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="29c33-110">Return Value</span></span>  

 <span data-ttu-id="29c33-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="29c33-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="29c33-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="29c33-112">HRESULT</span></span>|<span data-ttu-id="29c33-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="29c33-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="29c33-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="29c33-114">S_OK</span></span>|<span data-ttu-id="29c33-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="29c33-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="29c33-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="29c33-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="29c33-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="29c33-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29c33-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="29c33-118">Remarks</span></span>  

 <span data-ttu-id="29c33-119">Actualmente, el único valor definido para `dwInitializeDomainFlags` es `eInitializeNewDomainFlags_NoSecurityChanges` , que indica al Common Language Runtime (CLR) que el administrador del dominio de aplicación no modificará la configuración de seguridad durante la ejecución del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="29c33-119">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="29c33-120">Esto permite que CLR optimice la carga de ensamblados que tienen el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo condicional (APTCA).</span><span class="sxs-lookup"><span data-stu-id="29c33-120">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="29c33-121">Esto puede dar lugar a una mejora significativa en el tiempo de inicio si el cierre transitivo de este conjunto de ensamblados es grande.</span><span class="sxs-lookup"><span data-stu-id="29c33-121">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="29c33-122">Si el host especifica `eInitializeNewDomainFlags_NoSecurityChanges` para el administrador del dominio de aplicación, <xref:System.InvalidOperationException> se produce una excepción si se intenta modificar la seguridad del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29c33-122">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="29c33-123">Llamar al método [ICLRControl:: setappdomainmanagertype (](iclrcontrol-setappdomainmanagertype-method.md)es equivalente a llamar a `ICLRDomainManager::SetAppDomainManagerType` con `eInitializeNewDomainFlags_None` .</span><span class="sxs-lookup"><span data-stu-id="29c33-123">Calling the [ICLRControl::SetAppDomainManagerType](iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29c33-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29c33-124">Requirements</span></span>  

 <span data-ttu-id="29c33-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29c33-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29c33-126">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="29c33-126">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="29c33-127">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="29c33-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29c33-128">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29c33-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c33-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="29c33-129">See also</span></span>

- [<span data-ttu-id="29c33-130">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="29c33-130">Hosting</span></span>](index.md)
- [<span data-ttu-id="29c33-131">ICLRDomainManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="29c33-131">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
- [<span data-ttu-id="29c33-132">EInitializeNewDomainFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="29c33-132">EInitializeNewDomainFlags Enumeration</span></span>](einitializenewdomainflags-enumeration.md)
