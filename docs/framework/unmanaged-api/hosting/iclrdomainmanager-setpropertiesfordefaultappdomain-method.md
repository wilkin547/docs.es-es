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
ms.openlocfilehash: b5577d0444caf14fb47d9d7e2de60a8399378db7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702139"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="8093a-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="8093a-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>

<span data-ttu-id="8093a-103">Establece las propiedades que se usarán para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8093a-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8093a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8093a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8093a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8093a-105">Parameters</span></span>  

 `nProperties`  
 <span data-ttu-id="8093a-106">de Número de entradas en `pwszPropertyNames` y `pwszPropertyValues` .</span><span class="sxs-lookup"><span data-stu-id="8093a-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="8093a-107">de Una matriz de nombres de propiedad, o null si no hay propiedades.</span><span class="sxs-lookup"><span data-stu-id="8093a-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="8093a-108">Actualmente, el único nombre de propiedad que reconoce este método es "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="8093a-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="8093a-109">de Una matriz de valores de propiedad o null si no hay propiedades.</span><span class="sxs-lookup"><span data-stu-id="8093a-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8093a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8093a-110">Return Value</span></span>  

 <span data-ttu-id="8093a-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="8093a-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8093a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8093a-112">HRESULT</span></span>|<span data-ttu-id="8093a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8093a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8093a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="8093a-114">S_OK</span></span>|<span data-ttu-id="8093a-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8093a-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="8093a-116">HRESULT_FROM_WIN32 (ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="8093a-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="8093a-117">`pwszPropertyNames` incluye un nombre de propiedad que este método no reconoce.</span><span class="sxs-lookup"><span data-stu-id="8093a-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8093a-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8093a-118">Remarks</span></span>  

 <span data-ttu-id="8093a-119">El valor de propiedad para "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" es una lista de ensamblados que tienen el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo condicional (APTCA) con la <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> marca, que se van a hacer visibles para los llamadores de confianza parcial en el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8093a-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8093a-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8093a-120">Requirements</span></span>  

 <span data-ttu-id="8093a-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8093a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8093a-122">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="8093a-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8093a-123">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8093a-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8093a-124">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8093a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8093a-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8093a-125">See also</span></span>

- [<span data-ttu-id="8093a-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="8093a-126">Hosting</span></span>](index.md)
- [<span data-ttu-id="8093a-127">ICLRDomainManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8093a-127">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
