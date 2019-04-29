---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 69fcc862e98e305105a6f17ca49940bd10cef39c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937064"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="4ae9f-102">ICorRuntimeHost::EnumDomains (Método)</span><span class="sxs-lookup"><span data-stu-id="4ae9f-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="4ae9f-103">Obtiene un enumerador para los dominios en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="4ae9f-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ae9f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ae9f-104">Syntax</span></span>  
  
```  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ae9f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ae9f-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="4ae9f-106">[out] Un enumerador para los dominios.</span><span class="sxs-lookup"><span data-stu-id="4ae9f-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ae9f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4ae9f-107">Return Value</span></span>  
  
|<span data-ttu-id="4ae9f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ae9f-108">HRESULT</span></span>|<span data-ttu-id="4ae9f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ae9f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4ae9f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ae9f-110">S_OK</span></span>|<span data-ttu-id="4ae9f-111">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="4ae9f-111">The operation was successful.</span></span>|  
|<span data-ttu-id="4ae9f-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4ae9f-112">S_FALSE</span></span>|<span data-ttu-id="4ae9f-113">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="4ae9f-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="4ae9f-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4ae9f-114">E_FAIL</span></span>|<span data-ttu-id="4ae9f-115">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="4ae9f-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="4ae9f-116">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4ae9f-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="4ae9f-117">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4ae9f-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4ae9f-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4ae9f-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4ae9f-119">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4ae9f-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4ae9f-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ae9f-120">Requirements</span></span>  
 <span data-ttu-id="4ae9f-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ae9f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ae9f-122">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4ae9f-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ae9f-123">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4ae9f-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ae9f-124">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="4ae9f-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ae9f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ae9f-125">See also</span></span>

- [<span data-ttu-id="4ae9f-126">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4ae9f-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
