---
description: 'Más información sobre: ICorRuntimeHost:: CreateDomainSetup ((método)'
title: ICorRuntimeHost::CreateDomainSetup (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: b7c2dc55fa9f0d3d5a5c18e38c2c825048ae5f53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789689"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="63d94-103">ICorRuntimeHost::CreateDomainSetup (Método)</span><span class="sxs-lookup"><span data-stu-id="63d94-103">ICorRuntimeHost::CreateDomainSetup Method</span></span>

<span data-ttu-id="63d94-104">Obtiene un puntero de interfaz de tipo IAppDomainSetup a una <xref:System.AppDomainSetup?displayProperty=nameWithType> instancia de.</span><span class="sxs-lookup"><span data-stu-id="63d94-104">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="63d94-105">`IAppDomainSetup` proporciona métodos para configurar aspectos de un dominio de aplicación antes de que se cree.</span><span class="sxs-lookup"><span data-stu-id="63d94-105">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d94-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63d94-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63d94-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63d94-107">Parameters</span></span>  

 `pAppDomainSetup`  
 <span data-ttu-id="63d94-108">enuncia Puntero de interfaz a una <xref:System.AppDomainSetup?displayProperty=nameWithType> instancia de.</span><span class="sxs-lookup"><span data-stu-id="63d94-108">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="63d94-109">Este parámetro tiene el tipo `IUnknown` , por lo que los llamadores generalmente deben llamar a `QueryInterface` en este puntero para obtener un puntero de interfaz de tipo `IAppDomainSetup` .</span><span class="sxs-lookup"><span data-stu-id="63d94-109">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63d94-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="63d94-110">Return Value</span></span>  
  
|<span data-ttu-id="63d94-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63d94-111">HRESULT</span></span>|<span data-ttu-id="63d94-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="63d94-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63d94-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="63d94-113">S_OK</span></span>|<span data-ttu-id="63d94-114">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="63d94-114">The operation was successful.</span></span>|  
|<span data-ttu-id="63d94-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="63d94-115">S_FALSE</span></span>|<span data-ttu-id="63d94-116">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="63d94-116">The operation failed to complete.</span></span>|  
|<span data-ttu-id="63d94-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="63d94-117">E_FAIL</span></span>|<span data-ttu-id="63d94-118">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="63d94-118">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="63d94-119">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="63d94-119">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="63d94-120">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="63d94-120">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="63d94-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="63d94-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="63d94-122">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="63d94-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63d94-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="63d94-123">Remarks</span></span>  

 <span data-ttu-id="63d94-124">Normalmente, el puntero devuelto por este método se pasa como un parámetro al método [createdomainex (](icorruntimehost-createdomainex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="63d94-124">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d94-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63d94-125">Requirements</span></span>  

 <span data-ttu-id="63d94-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63d94-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d94-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="63d94-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63d94-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="63d94-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63d94-129">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="63d94-129">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d94-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="63d94-130">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="63d94-131">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="63d94-131">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
