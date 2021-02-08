---
description: 'Más información sobre: ICorRuntimeHost:: UnloadDomain ((método)'
title: ICorRuntimeHost::UnloadDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
ms.openlocfilehash: b191f2342778b2f2ed7ddb7b1fb548c73be96599
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799402"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="f85ba-103">ICorRuntimeHost::UnloadDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="f85ba-103">ICorRuntimeHost::UnloadDomain Method</span></span>

<span data-ttu-id="f85ba-104">Descarga el dominio de aplicación especificado del proceso actual.</span><span class="sxs-lookup"><span data-stu-id="f85ba-104">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f85ba-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f85ba-105">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f85ba-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f85ba-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="f85ba-107">de Puntero de tipo <xref:System._AppDomain?displayProperty=nameWithType> que representa el dominio que se va a descargar.</span><span class="sxs-lookup"><span data-stu-id="f85ba-107">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f85ba-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f85ba-108">Return Value</span></span>  
  
|<span data-ttu-id="f85ba-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f85ba-109">HRESULT</span></span>|<span data-ttu-id="f85ba-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f85ba-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f85ba-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f85ba-111">S_OK</span></span>|<span data-ttu-id="f85ba-112">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f85ba-112">The operation was successful.</span></span>|  
|<span data-ttu-id="f85ba-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f85ba-113">S_FALSE</span></span>|<span data-ttu-id="f85ba-114">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="f85ba-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="f85ba-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f85ba-115">E_FAIL</span></span>|<span data-ttu-id="f85ba-116">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f85ba-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="f85ba-117">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f85ba-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="f85ba-118">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f85ba-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f85ba-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f85ba-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f85ba-120">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f85ba-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f85ba-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f85ba-121">Requirements</span></span>  

 <span data-ttu-id="f85ba-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f85ba-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f85ba-123">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f85ba-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f85ba-124">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f85ba-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f85ba-125">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="f85ba-125">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f85ba-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f85ba-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="f85ba-127">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f85ba-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
