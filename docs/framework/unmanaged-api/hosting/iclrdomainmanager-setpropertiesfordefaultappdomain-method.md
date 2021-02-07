---
description: 'Más información sobre: ICLRDomainManager:: SetPropertiesForDefaultAppDomain ((método)'
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
ms.openlocfilehash: 08e6c885d5d089fa22c30a4e3cef69480b840031
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689448"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="0cb9e-103">ICLRDomainManager::SetPropertiesForDefaultAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="0cb9e-103">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>

<span data-ttu-id="0cb9e-104">Establece las propiedades que se usarán para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0cb9e-104">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cb9e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0cb9e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cb9e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0cb9e-106">Parameters</span></span>  

 `nProperties`  
 <span data-ttu-id="0cb9e-107">de Número de entradas en `pwszPropertyNames` y `pwszPropertyValues` .</span><span class="sxs-lookup"><span data-stu-id="0cb9e-107">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="0cb9e-108">de Una matriz de nombres de propiedad, o null si no hay propiedades.</span><span class="sxs-lookup"><span data-stu-id="0cb9e-108">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="0cb9e-109">Actualmente, el único nombre de propiedad que reconoce este método es "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="0cb9e-109">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="0cb9e-110">de Una matriz de valores de propiedad o null si no hay propiedades.</span><span class="sxs-lookup"><span data-stu-id="0cb9e-110">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0cb9e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0cb9e-111">Return Value</span></span>  

 <span data-ttu-id="0cb9e-112">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="0cb9e-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0cb9e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0cb9e-113">HRESULT</span></span>|<span data-ttu-id="0cb9e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cb9e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0cb9e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="0cb9e-115">S_OK</span></span>|<span data-ttu-id="0cb9e-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="0cb9e-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="0cb9e-117">HRESULT_FROM_WIN32 (ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="0cb9e-117">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="0cb9e-118">`pwszPropertyNames` incluye un nombre de propiedad que este método no reconoce.</span><span class="sxs-lookup"><span data-stu-id="0cb9e-118">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cb9e-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0cb9e-119">Remarks</span></span>  

 <span data-ttu-id="0cb9e-120">El valor de propiedad para "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" es una lista de ensamblados que tienen el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo condicional (APTCA) con la <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> marca, que se van a hacer visibles para los llamadores de confianza parcial en el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0cb9e-120">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cb9e-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0cb9e-121">Requirements</span></span>  

 <span data-ttu-id="0cb9e-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cb9e-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cb9e-123">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="0cb9e-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0cb9e-124">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0cb9e-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cb9e-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cb9e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cb9e-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cb9e-126">See also</span></span>

- [<span data-ttu-id="0cb9e-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="0cb9e-127">Hosting</span></span>](index.md)
- [<span data-ttu-id="0cb9e-128">ICLRDomainManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0cb9e-128">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
