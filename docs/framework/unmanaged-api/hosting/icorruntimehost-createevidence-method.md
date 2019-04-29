---
title: ICorRuntimeHost::CreateEvidence (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca54f779d257314b843838d90ca9996f1eb3237b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936908"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="80fb6-102">ICorRuntimeHost::CreateEvidence (Método)</span><span class="sxs-lookup"><span data-stu-id="80fb6-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="80fb6-103">Obtiene un puntero de interfaz de tipo <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, que permite al host crear la evidencia de seguridad para pasar a la [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) o [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="80fb6-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80fb6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80fb6-104">Syntax</span></span>  
  
```  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80fb6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80fb6-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="80fb6-106">[out] Un puntero de interfaz a un <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instancia utilizada para crear la evidencia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="80fb6-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="80fb6-107">Este puntero es de tipo `IUnknown`, por lo que normalmente deben llamar los llamadores `QueryInterface` en esta interfaz para obtener un puntero a un <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="80fb6-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80fb6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="80fb6-108">Return Value</span></span>  
  
|<span data-ttu-id="80fb6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80fb6-109">HRESULT</span></span>|<span data-ttu-id="80fb6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="80fb6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80fb6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="80fb6-111">S_OK</span></span>|<span data-ttu-id="80fb6-112">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="80fb6-112">The operation was successful.</span></span>|  
|<span data-ttu-id="80fb6-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="80fb6-113">S_FALSE</span></span>|<span data-ttu-id="80fb6-114">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="80fb6-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="80fb6-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="80fb6-115">E_FAIL</span></span>|<span data-ttu-id="80fb6-116">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="80fb6-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="80fb6-117">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="80fb6-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="80fb6-118">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="80fb6-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="80fb6-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="80fb6-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="80fb6-120">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="80fb6-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80fb6-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80fb6-121">Remarks</span></span>  
 <span data-ttu-id="80fb6-122">Este método devuelve una colección vacía que no se pueden rellenar desde código nativo.</span><span class="sxs-lookup"><span data-stu-id="80fb6-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="80fb6-123">Debe usar el <xref:System.Security.Policy.Evidence> método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="80fb6-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80fb6-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80fb6-124">Requirements</span></span>  
 <span data-ttu-id="80fb6-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80fb6-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80fb6-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="80fb6-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80fb6-127">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80fb6-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80fb6-128">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="80fb6-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80fb6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="80fb6-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="80fb6-130">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="80fb6-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
