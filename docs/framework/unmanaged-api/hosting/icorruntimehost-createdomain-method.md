---
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
ms.openlocfilehash: 74f17c77e74edb1226dda2d9ebaa9486e1769ce4
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762362"
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="50c68-102">ICorRuntimeHost::CreateDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="50c68-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="50c68-103">Crea un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="50c68-103">Creates an application domain.</span></span> <span data-ttu-id="50c68-104">El autor de la llamada recibe un puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="50c68-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50c68-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50c68-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50c68-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="50c68-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="50c68-107">de Parámetro opcional que se usa para proporcionar un nombre descriptivo al dominio.</span><span class="sxs-lookup"><span data-stu-id="50c68-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="50c68-108">Este nombre descriptivo puede mostrarse en las interfaces de usuario como depuradores para identificar el dominio.</span><span class="sxs-lookup"><span data-stu-id="50c68-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="50c68-109">de Matriz opcional de punteros a `IIdentity` instancias que representan la evidencia asignada a través de la Directiva de seguridad para establecer un conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="50c68-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="50c68-110">Un `IIdentity` objeto se puede obtener llamando al método [createevidence (](icorruntimehost-createevidence-method.md) .</span><span class="sxs-lookup"><span data-stu-id="50c68-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="50c68-111">enuncia Puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de <xref:System.AppDomain?displayProperty=nameWithType> que se puede utilizar para controlar aún más el dominio.</span><span class="sxs-lookup"><span data-stu-id="50c68-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50c68-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="50c68-112">Return Value</span></span>  
  
|<span data-ttu-id="50c68-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50c68-113">HRESULT</span></span>|<span data-ttu-id="50c68-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="50c68-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50c68-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="50c68-115">S_OK</span></span>|<span data-ttu-id="50c68-116">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="50c68-116">The operation was successful.</span></span>|  
|<span data-ttu-id="50c68-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="50c68-117">S_FALSE</span></span>|<span data-ttu-id="50c68-118">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="50c68-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="50c68-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50c68-119">E_FAIL</span></span>|<span data-ttu-id="50c68-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="50c68-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="50c68-121">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="50c68-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="50c68-122">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="50c68-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="50c68-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50c68-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50c68-124">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="50c68-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50c68-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50c68-125">Requirements</span></span>  
 <span data-ttu-id="50c68-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50c68-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50c68-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="50c68-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50c68-128">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="50c68-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50c68-129">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="50c68-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c68-130">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="50c68-130">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="50c68-131">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50c68-131">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
