---
description: 'Más información sobre: ICorRuntimeHost:: EnumDomains ((método)'
title: ICorRuntimeHost::EnumDomains (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.EnumDomains
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type:
- apiref
ms.openlocfilehash: e581fe95a78a4f55d50a99e4925e03a1777268a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784878"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="656a2-103">ICorRuntimeHost::EnumDomains (Método)</span><span class="sxs-lookup"><span data-stu-id="656a2-103">ICorRuntimeHost::EnumDomains Method</span></span>

<span data-ttu-id="656a2-104">Obtiene un enumerador para los dominios en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="656a2-104">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="656a2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="656a2-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="656a2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="656a2-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="656a2-107">enuncia Un enumerador para los dominios.</span><span class="sxs-lookup"><span data-stu-id="656a2-107">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="656a2-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="656a2-108">Return Value</span></span>  
  
|<span data-ttu-id="656a2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="656a2-109">HRESULT</span></span>|<span data-ttu-id="656a2-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="656a2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="656a2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="656a2-111">S_OK</span></span>|<span data-ttu-id="656a2-112">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="656a2-112">The operation was successful.</span></span>|  
|<span data-ttu-id="656a2-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="656a2-113">S_FALSE</span></span>|<span data-ttu-id="656a2-114">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="656a2-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="656a2-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="656a2-115">E_FAIL</span></span>|<span data-ttu-id="656a2-116">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="656a2-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="656a2-117">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="656a2-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="656a2-118">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="656a2-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="656a2-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="656a2-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="656a2-120">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="656a2-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="656a2-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="656a2-121">Requirements</span></span>  

 <span data-ttu-id="656a2-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="656a2-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="656a2-123">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="656a2-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="656a2-124">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="656a2-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="656a2-125">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="656a2-125">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="656a2-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="656a2-126">See also</span></span>

- [<span data-ttu-id="656a2-127">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="656a2-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
