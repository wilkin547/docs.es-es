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
ms.openlocfilehash: 5e1c1b1984c63bedb3c073f45a7b9a3574afdcec
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615688"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="d2ea4-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="d2ea4-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="d2ea4-103">Establece las propiedades que se usarán para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d2ea4-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2ea4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2ea4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2ea4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2ea4-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="d2ea4-106">de Número de entradas en `pwszPropertyNames` y `pwszPropertyValues` .</span><span class="sxs-lookup"><span data-stu-id="d2ea4-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="d2ea4-107">de Una matriz de nombres de propiedad, o null si no hay propiedades.</span><span class="sxs-lookup"><span data-stu-id="d2ea4-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="d2ea4-108">Actualmente, el único nombre de propiedad que reconoce este método es "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="d2ea4-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="d2ea4-109">de Una matriz de valores de propiedad o null si no hay propiedades.</span><span class="sxs-lookup"><span data-stu-id="d2ea4-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2ea4-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d2ea4-110">Return Value</span></span>  
 <span data-ttu-id="d2ea4-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="d2ea4-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d2ea4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d2ea4-112">HRESULT</span></span>|<span data-ttu-id="d2ea4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2ea4-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d2ea4-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2ea4-114">S_OK</span></span>|<span data-ttu-id="d2ea4-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d2ea4-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="d2ea4-116">HRESULT_FROM_WIN32 (ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="d2ea4-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="d2ea4-117">`pwszPropertyNames`incluye un nombre de propiedad que este método no reconoce.</span><span class="sxs-lookup"><span data-stu-id="d2ea4-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2ea4-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d2ea4-118">Remarks</span></span>  
 <span data-ttu-id="d2ea4-119">El valor de propiedad para "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" es una lista de ensamblados que tienen el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo condicional (APTCA) con la <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> marca, que se van a hacer visibles para los llamadores de confianza parcial en el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d2ea4-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2ea4-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2ea4-120">Requirements</span></span>  
 <span data-ttu-id="d2ea4-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2ea4-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2ea4-122">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d2ea4-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d2ea4-123">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d2ea4-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2ea4-124">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2ea4-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2ea4-125">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d2ea4-125">See also</span></span>

- [<span data-ttu-id="d2ea4-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="d2ea4-126">Hosting</span></span>](index.md)
- [<span data-ttu-id="d2ea4-127">ICLRDomainManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2ea4-127">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
