---
description: 'Más información acerca de: ICorRuntimeHost:: CreateDomain (método)'
title: ICorRuntimeHost::CreateDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
ms.openlocfilehash: 6173d74d97ddb9dec619db8583036ec763a9e293
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789715"
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="a450b-103">ICorRuntimeHost::CreateDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="a450b-103">ICorRuntimeHost::CreateDomain Method</span></span>

<span data-ttu-id="a450b-104">Crea un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a450b-104">Creates an application domain.</span></span> <span data-ttu-id="a450b-105">El autor de la llamada recibe un puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a450b-105">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a450b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a450b-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a450b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a450b-107">Parameters</span></span>  

 `pwzFriendlyName`  
 <span data-ttu-id="a450b-108">de Parámetro opcional que se usa para proporcionar un nombre descriptivo al dominio.</span><span class="sxs-lookup"><span data-stu-id="a450b-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="a450b-109">Este nombre descriptivo puede mostrarse en las interfaces de usuario como depuradores para identificar el dominio.</span><span class="sxs-lookup"><span data-stu-id="a450b-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="a450b-110">de Matriz opcional de punteros a `IIdentity` instancias que representan la evidencia asignada a través de la Directiva de seguridad para establecer un conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="a450b-110">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="a450b-111">Un `IIdentity` objeto se puede obtener llamando al método [createevidence (](icorruntimehost-createevidence-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a450b-111">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="a450b-112">enuncia Puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de <xref:System.AppDomain?displayProperty=nameWithType> que se puede utilizar para controlar aún más el dominio.</span><span class="sxs-lookup"><span data-stu-id="a450b-112">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a450b-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a450b-113">Return Value</span></span>  
  
|<span data-ttu-id="a450b-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a450b-114">HRESULT</span></span>|<span data-ttu-id="a450b-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a450b-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a450b-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a450b-116">S_OK</span></span>|<span data-ttu-id="a450b-117">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a450b-117">The operation was successful.</span></span>|  
|<span data-ttu-id="a450b-118">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a450b-118">S_FALSE</span></span>|<span data-ttu-id="a450b-119">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="a450b-119">The operation failed to complete.</span></span>|  
|<span data-ttu-id="a450b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a450b-120">E_FAIL</span></span>|<span data-ttu-id="a450b-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a450b-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a450b-122">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a450b-122">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="a450b-123">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a450b-123">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a450b-124">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a450b-124">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a450b-125">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a450b-125">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a450b-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a450b-126">Requirements</span></span>  

 <span data-ttu-id="a450b-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a450b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a450b-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a450b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a450b-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a450b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a450b-130">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="a450b-130">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a450b-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a450b-131">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="a450b-132">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a450b-132">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
