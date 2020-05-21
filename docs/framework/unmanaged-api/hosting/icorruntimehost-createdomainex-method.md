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
ms.openlocfilehash: 4e5856fbcda83c1dd30559c6f59f63495faea78d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762349"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="a9974-102">ICorRuntimeHost::CreateDomainEx (Método)</span><span class="sxs-lookup"><span data-stu-id="a9974-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="a9974-103">Crea un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9974-103">Creates an application domain.</span></span> <span data-ttu-id="a9974-104">El autor de la llamada recibe un puntero de interfaz, de tipo <xref:System._AppDomain> , a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a9974-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a9974-105">Este método permite al llamador pasar una instancia de IAppDomainSetup para configurar características adicionales de la instancia de devuelta <xref:System._AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="a9974-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9974-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9974-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9974-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9974-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="a9974-108">de Parámetro opcional que se usa para proporcionar un nombre descriptivo al dominio.</span><span class="sxs-lookup"><span data-stu-id="a9974-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="a9974-109">Este nombre descriptivo puede mostrarse en las interfaces de usuario como depuradores para identificar el dominio.</span><span class="sxs-lookup"><span data-stu-id="a9974-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="a9974-110">de Un puntero de interfaz opcional de tipo `IAppDomainSetup` , obtenido mediante una llamada al método [ICorRuntimeHost:: CreateDomainSetup (](icorruntimehost-createdomainsetup-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a9974-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="a9974-111">de Matriz opcional de punteros a `IIdentity` instancias que representan la evidencia asignada a través de la Directiva de seguridad para establecer un conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="a9974-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="a9974-112">Un `IIdentity` objeto se puede obtener llamando al método [createevidence (](icorruntimehost-createevidence-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a9974-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="a9974-113">enuncia Puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de <xref:System.AppDomain?displayProperty=nameWithType> que se puede utilizar para controlar aún más el dominio.</span><span class="sxs-lookup"><span data-stu-id="a9974-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9974-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a9974-114">Return Value</span></span>  
  
|<span data-ttu-id="a9974-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9974-115">HRESULT</span></span>|<span data-ttu-id="a9974-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9974-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9974-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9974-117">S_OK</span></span>|<span data-ttu-id="a9974-118">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a9974-118">The operation was successful.</span></span>|  
|<span data-ttu-id="a9974-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a9974-119">S_FALSE</span></span>|<span data-ttu-id="a9974-120">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="a9974-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="a9974-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a9974-121">E_FAIL</span></span>|<span data-ttu-id="a9974-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a9974-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a9974-123">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a9974-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="a9974-124">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a9974-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a9974-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a9974-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a9974-126">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a9974-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9974-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9974-127">Remarks</span></span>  
 <span data-ttu-id="a9974-128">`CreateDomainEx`extiende las capacidades de [CreateDomain](icorruntimehost-createdomain-method.md) permitiendo que el llamador pase una `IAppDomainSetup` instancia con valores de propiedad para configurar el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9974-128">`CreateDomainEx` extends the capabilities of [CreateDomain](icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9974-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9974-129">Requirements</span></span>  
 <span data-ttu-id="a9974-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9974-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9974-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a9974-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9974-132">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a9974-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9974-133">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="a9974-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9974-134">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="a9974-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="a9974-135">Método CreateDomain</span><span class="sxs-lookup"><span data-stu-id="a9974-135">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="a9974-136">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9974-136">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
