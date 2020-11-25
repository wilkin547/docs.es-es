---
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
ms.openlocfilehash: 7c6b328793e6437682ad8d642e611be30e7b0fe6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702153"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="c722a-102">ICLRDomainManager::SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="c722a-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>

<span data-ttu-id="c722a-103">Especifica el tipo, derivado de la <xref:System.AppDomainManager?displayProperty=nameWithType> clase, del administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c722a-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c722a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c722a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c722a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c722a-105">Parameters</span></span>  

 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="c722a-106">de El nombre para mostrar del ensamblado que contiene el tipo de administrador de dominio de aplicación; por ejemplo: "AdMgrExample, version = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf150f00b3".</span><span class="sxs-lookup"><span data-stu-id="c722a-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="c722a-107">de El nombre de tipo del administrador del dominio de aplicación, incluido el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c722a-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="c722a-108">de Combinación de valores de enumeración de [einitializenewdomainflags (](einitializenewdomainflags-enumeration.md) que proporcionan información sobre el administrador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c722a-108">[in] A combination of [EInitializeNewDomainFlags](einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c722a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c722a-109">Return Value</span></span>  

 <span data-ttu-id="c722a-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="c722a-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c722a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c722a-111">HRESULT</span></span>|<span data-ttu-id="c722a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c722a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c722a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c722a-113">S_OK</span></span>|<span data-ttu-id="c722a-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c722a-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="c722a-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c722a-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c722a-116">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c722a-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c722a-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c722a-117">Remarks</span></span>  

 <span data-ttu-id="c722a-118">Actualmente, el único valor definido para `dwInitializeDomainFlags` es `eInitializeNewDomainFlags_NoSecurityChanges` , que indica al Common Language Runtime (CLR) que el administrador del dominio de aplicación no modificará la configuración de seguridad durante la ejecución del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="c722a-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c722a-119">Esto permite que CLR optimice la carga de ensamblados que tienen el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo condicional (APTCA).</span><span class="sxs-lookup"><span data-stu-id="c722a-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="c722a-120">Esto puede dar lugar a una mejora significativa en el tiempo de inicio si el cierre transitivo de este conjunto de ensamblados es grande.</span><span class="sxs-lookup"><span data-stu-id="c722a-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c722a-121">Si el host especifica `eInitializeNewDomainFlags_NoSecurityChanges` para el administrador del dominio de aplicación, <xref:System.InvalidOperationException> se produce una excepción si se intenta modificar la seguridad del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c722a-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="c722a-122">Llamar al método [ICLRControl:: setappdomainmanagertype (](iclrcontrol-setappdomainmanagertype-method.md)es equivalente a llamar a `ICLRDomainManager::SetAppDomainManagerType` con `eInitializeNewDomainFlags_None` .</span><span class="sxs-lookup"><span data-stu-id="c722a-122">Calling the [ICLRControl::SetAppDomainManagerType](iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c722a-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c722a-123">Requirements</span></span>  

 <span data-ttu-id="c722a-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c722a-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c722a-125">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="c722a-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c722a-126">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c722a-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c722a-127">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c722a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c722a-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c722a-128">See also</span></span>

- [<span data-ttu-id="c722a-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="c722a-129">Hosting</span></span>](index.md)
- [<span data-ttu-id="c722a-130">ICLRDomainManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c722a-130">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
- [<span data-ttu-id="c722a-131">EInitializeNewDomainFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c722a-131">EInitializeNewDomainFlags Enumeration</span></span>](einitializenewdomainflags-enumeration.md)
