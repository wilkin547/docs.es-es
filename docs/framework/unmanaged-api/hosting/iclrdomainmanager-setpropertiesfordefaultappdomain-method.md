---
title: ICLRDomainManager::SetPropertiesForDefaultAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
ms.openlocfilehash: 37919be2d0ebd7d243615bc5845b0781ac13e574
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129312"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="2e284-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="2e284-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="2e284-103">Establece las propiedades que se usarán para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2e284-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e284-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e284-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e284-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2e284-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="2e284-106">de Número de entradas de `pwszPropertyNames` y `pwszPropertyValues`.</span><span class="sxs-lookup"><span data-stu-id="2e284-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="2e284-107">de Una matriz de nombres de propiedad, o null si no hay propiedades.</span><span class="sxs-lookup"><span data-stu-id="2e284-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="2e284-108">Actualmente, el único nombre de propiedad que reconoce este método es "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="2e284-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="2e284-109">de Una matriz de valores de propiedad o null si no hay propiedades.</span><span class="sxs-lookup"><span data-stu-id="2e284-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e284-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2e284-110">Return Value</span></span>  
 <span data-ttu-id="2e284-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="2e284-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2e284-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e284-112">HRESULT</span></span>|<span data-ttu-id="2e284-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e284-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e284-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e284-114">S_OK</span></span>|<span data-ttu-id="2e284-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="2e284-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="2e284-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="2e284-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="2e284-117">`pwszPropertyNames` incluye un nombre de propiedad que este método no reconoce.</span><span class="sxs-lookup"><span data-stu-id="2e284-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e284-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2e284-118">Remarks</span></span>  
 <span data-ttu-id="2e284-119">El valor de propiedad para "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" es una lista de ensamblados que tienen el atributo de <xref:System.Security.AllowPartiallyTrustedCallersAttribute> condicional (APTCA) con la marca <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType>, que se van a hacer visibles para los llamadores de confianza parcial en el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2e284-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e284-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e284-120">Requirements</span></span>  
 <span data-ttu-id="2e284-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e284-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e284-122">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="2e284-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2e284-123">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2e284-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e284-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e284-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e284-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e284-125">See also</span></span>

- [<span data-ttu-id="2e284-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="2e284-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="2e284-127">ICLRDomainManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e284-127">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
