---
title: ICorRuntimeHost::NextDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
ms.openlocfilehash: 36eacedfb83c1248fc252091872bcfeecdbcd874
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139521"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="e3fd0-102">ICorRuntimeHost::NextDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="e3fd0-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="e3fd0-103">Obtiene un puntero de interfaz al siguiente dominio en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="e3fd0-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3fd0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3fd0-104">Syntax</span></span>  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3fd0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e3fd0-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="e3fd0-106">de Enumerador que se obtuvo a través de una llamada a [EnumDomains (](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="e3fd0-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="e3fd0-107">enuncia Puntero de interfaz al tipo de <xref:System._AppDomain?displayProperty=nameWithType> que representa el siguiente dominio de la enumeración, o null si no existen más dominios.</span><span class="sxs-lookup"><span data-stu-id="e3fd0-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3fd0-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e3fd0-108">Return Value</span></span>  
  
|<span data-ttu-id="e3fd0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3fd0-109">HRESULT</span></span>|<span data-ttu-id="e3fd0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3fd0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3fd0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3fd0-111">S_OK</span></span>|<span data-ttu-id="e3fd0-112">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e3fd0-112">The operation was successful.</span></span>|  
|<span data-ttu-id="e3fd0-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e3fd0-113">S_FALSE</span></span>|<span data-ttu-id="e3fd0-114">No se pudo completar la operación o no hay más dominios en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="e3fd0-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="e3fd0-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e3fd0-115">E_FAIL</span></span>|<span data-ttu-id="e3fd0-116">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e3fd0-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e3fd0-117">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e3fd0-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e3fd0-118">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e3fd0-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e3fd0-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e3fd0-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e3fd0-120">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e3fd0-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3fd0-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3fd0-121">Requirements</span></span>  
 <span data-ttu-id="e3fd0-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3fd0-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3fd0-123">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e3fd0-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3fd0-124">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e3fd0-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3fd0-125">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e3fd0-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3fd0-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3fd0-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="e3fd0-127">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3fd0-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
