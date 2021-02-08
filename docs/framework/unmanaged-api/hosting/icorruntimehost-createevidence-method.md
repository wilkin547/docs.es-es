---
description: 'Más información sobre: ICorRuntimeHost:: Createevidence ((método)'
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
ms.openlocfilehash: 34694f7e867066430a28120b412237ef9c64c740
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789676"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="f3d79-103">ICorRuntimeHost::CreateEvidence (Método)</span><span class="sxs-lookup"><span data-stu-id="f3d79-103">ICorRuntimeHost::CreateEvidence Method</span></span>

<span data-ttu-id="f3d79-104">Obtiene un puntero de interfaz de tipo <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> , que permite al host crear la evidencia de seguridad que se va a pasar al método [CreateDomain](icorruntimehost-createdomain-method.md) o [createdomainex (](icorruntimehost-createdomainex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f3d79-104">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](icorruntimehost-createdomain-method.md) or [CreateDomainEx](icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3d79-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3d79-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3d79-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3d79-106">Parameters</span></span>  

 `pEvidence`  
 <span data-ttu-id="f3d79-107">enuncia Puntero de interfaz a una <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instancia de utilizada para crear la evidencia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f3d79-107">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="f3d79-108">Este puntero tiene tipo `IUnknown` , por lo que los llamadores normalmente deben llamar a `QueryInterface` en esta interfaz para obtener un puntero a <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f3d79-108">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3d79-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f3d79-109">Return Value</span></span>  
  
|<span data-ttu-id="f3d79-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f3d79-110">HRESULT</span></span>|<span data-ttu-id="f3d79-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3d79-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f3d79-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3d79-112">S_OK</span></span>|<span data-ttu-id="f3d79-113">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f3d79-113">The operation was successful.</span></span>|  
|<span data-ttu-id="f3d79-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f3d79-114">S_FALSE</span></span>|<span data-ttu-id="f3d79-115">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="f3d79-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="f3d79-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f3d79-116">E_FAIL</span></span>|<span data-ttu-id="f3d79-117">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f3d79-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="f3d79-118">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f3d79-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="f3d79-119">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f3d79-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f3d79-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f3d79-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f3d79-121">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f3d79-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3d79-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f3d79-122">Remarks</span></span>  

 <span data-ttu-id="f3d79-123">Este método devuelve una colección vacía que no se puede rellenar desde código nativo.</span><span class="sxs-lookup"><span data-stu-id="f3d79-123">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="f3d79-124">En su lugar, debe utilizar el <xref:System.Security.Policy.Evidence> método.</span><span class="sxs-lookup"><span data-stu-id="f3d79-124">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3d79-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3d79-125">Requirements</span></span>  

 <span data-ttu-id="f3d79-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3d79-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3d79-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f3d79-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3d79-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f3d79-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3d79-129">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="f3d79-129">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d79-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3d79-130">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="f3d79-131">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3d79-131">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
