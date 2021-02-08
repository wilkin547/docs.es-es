---
description: 'Más información sobre: ICorRuntimeHost:: Createdomainex ((método)'
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
ms.openlocfilehash: aec759cec4fd68fff4bdfaaf3403a0da026fb9ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789702"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="a1711-103">ICorRuntimeHost::CreateDomainEx (Método)</span><span class="sxs-lookup"><span data-stu-id="a1711-103">ICorRuntimeHost::CreateDomainEx Method</span></span>

<span data-ttu-id="a1711-104">Crea un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1711-104">Creates an application domain.</span></span> <span data-ttu-id="a1711-105">El autor de la llamada recibe un puntero de interfaz, de tipo <xref:System._AppDomain> , a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a1711-105">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a1711-106">Este método permite al llamador pasar una instancia de IAppDomainSetup para configurar características adicionales de la instancia de devuelta <xref:System._AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="a1711-106">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1711-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1711-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1711-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1711-108">Parameters</span></span>  

 `pwzFriendlyName`  
 <span data-ttu-id="a1711-109">de Parámetro opcional que se usa para proporcionar un nombre descriptivo al dominio.</span><span class="sxs-lookup"><span data-stu-id="a1711-109">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="a1711-110">Este nombre descriptivo puede mostrarse en las interfaces de usuario como depuradores para identificar el dominio.</span><span class="sxs-lookup"><span data-stu-id="a1711-110">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="a1711-111">de Un puntero de interfaz opcional de tipo `IAppDomainSetup` , obtenido mediante una llamada al método [ICorRuntimeHost:: CreateDomainSetup (](icorruntimehost-createdomainsetup-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a1711-111">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="a1711-112">de Matriz opcional de punteros a `IIdentity` instancias que representan la evidencia asignada a través de la Directiva de seguridad para establecer un conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="a1711-112">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="a1711-113">Un `IIdentity` objeto se puede obtener llamando al método [createevidence (](icorruntimehost-createevidence-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a1711-113">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="a1711-114">enuncia Puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de <xref:System.AppDomain?displayProperty=nameWithType> que se puede utilizar para controlar aún más el dominio.</span><span class="sxs-lookup"><span data-stu-id="a1711-114">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1711-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a1711-115">Return Value</span></span>  
  
|<span data-ttu-id="a1711-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1711-116">HRESULT</span></span>|<span data-ttu-id="a1711-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1711-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1711-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1711-118">S_OK</span></span>|<span data-ttu-id="a1711-119">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a1711-119">The operation was successful.</span></span>|  
|<span data-ttu-id="a1711-120">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a1711-120">S_FALSE</span></span>|<span data-ttu-id="a1711-121">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="a1711-121">The operation failed to complete.</span></span>|  
|<span data-ttu-id="a1711-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a1711-122">E_FAIL</span></span>|<span data-ttu-id="a1711-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a1711-123">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a1711-124">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a1711-124">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="a1711-125">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a1711-125">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a1711-126">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a1711-126">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a1711-127">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a1711-127">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1711-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a1711-128">Remarks</span></span>  

 <span data-ttu-id="a1711-129">`CreateDomainEx` extiende las capacidades de [CreateDomain](icorruntimehost-createdomain-method.md) permitiendo que el llamador pase una `IAppDomainSetup` instancia con valores de propiedad para configurar el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1711-129">`CreateDomainEx` extends the capabilities of [CreateDomain](icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1711-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1711-130">Requirements</span></span>  

 <span data-ttu-id="a1711-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1711-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1711-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a1711-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1711-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1711-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1711-134">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="a1711-134">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1711-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1711-135">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="a1711-136">Método CreateDomain</span><span class="sxs-lookup"><span data-stu-id="a1711-136">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="a1711-137">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1711-137">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
