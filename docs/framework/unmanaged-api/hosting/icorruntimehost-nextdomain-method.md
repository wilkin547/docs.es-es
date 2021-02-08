---
description: 'Más información sobre: ICorRuntimeHost:: NextDomain ((método)'
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
ms.openlocfilehash: cfced9d1d3c91f4ec9508b86157ceebae9f95a56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789624"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="00f2a-103">ICorRuntimeHost::NextDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="00f2a-103">ICorRuntimeHost::NextDomain Method</span></span>

<span data-ttu-id="00f2a-104">Obtiene un puntero de interfaz al siguiente dominio en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="00f2a-104">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00f2a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00f2a-105">Syntax</span></span>  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00f2a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="00f2a-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="00f2a-107">de Enumerador que se obtuvo a través de una llamada a [EnumDomains (](icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="00f2a-107">[in] The enumerator that was obtained through a call to [EnumDomains](icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="00f2a-108">enuncia Puntero de interfaz al <xref:System._AppDomain?displayProperty=nameWithType> tipo que representa el siguiente dominio en la enumeración, o null, si no existen más dominios.</span><span class="sxs-lookup"><span data-stu-id="00f2a-108">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00f2a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="00f2a-109">Return Value</span></span>  
  
|<span data-ttu-id="00f2a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="00f2a-110">HRESULT</span></span>|<span data-ttu-id="00f2a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="00f2a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00f2a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="00f2a-112">S_OK</span></span>|<span data-ttu-id="00f2a-113">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="00f2a-113">The operation was successful.</span></span>|  
|<span data-ttu-id="00f2a-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="00f2a-114">S_FALSE</span></span>|<span data-ttu-id="00f2a-115">No se pudo completar la operación o no hay más dominios en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="00f2a-115">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="00f2a-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="00f2a-116">E_FAIL</span></span>|<span data-ttu-id="00f2a-117">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="00f2a-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="00f2a-118">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="00f2a-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="00f2a-119">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="00f2a-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="00f2a-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="00f2a-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="00f2a-121">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="00f2a-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00f2a-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00f2a-122">Requirements</span></span>  

 <span data-ttu-id="00f2a-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00f2a-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00f2a-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="00f2a-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00f2a-125">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="00f2a-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00f2a-126">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="00f2a-126">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00f2a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="00f2a-127">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="00f2a-128">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00f2a-128">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
