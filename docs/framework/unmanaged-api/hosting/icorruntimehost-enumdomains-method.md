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
ms.openlocfilehash: f4338429dc24bf5196b92d3f18e73c98442f61e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720667"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="c4cfd-102">ICorRuntimeHost::EnumDomains (Método)</span><span class="sxs-lookup"><span data-stu-id="c4cfd-102">ICorRuntimeHost::EnumDomains Method</span></span>

<span data-ttu-id="c4cfd-103">Obtiene un enumerador para los dominios en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="c4cfd-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4cfd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4cfd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4cfd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4cfd-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="c4cfd-106">enuncia Un enumerador para los dominios.</span><span class="sxs-lookup"><span data-stu-id="c4cfd-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4cfd-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c4cfd-107">Return Value</span></span>  
  
|<span data-ttu-id="c4cfd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c4cfd-108">HRESULT</span></span>|<span data-ttu-id="c4cfd-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4cfd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4cfd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4cfd-110">S_OK</span></span>|<span data-ttu-id="c4cfd-111">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c4cfd-111">The operation was successful.</span></span>|  
|<span data-ttu-id="c4cfd-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c4cfd-112">S_FALSE</span></span>|<span data-ttu-id="c4cfd-113">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="c4cfd-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="c4cfd-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c4cfd-114">E_FAIL</span></span>|<span data-ttu-id="c4cfd-115">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c4cfd-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="c4cfd-116">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c4cfd-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="c4cfd-117">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c4cfd-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c4cfd-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c4cfd-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c4cfd-119">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c4cfd-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4cfd-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4cfd-120">Requirements</span></span>  

 <span data-ttu-id="c4cfd-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4cfd-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4cfd-122">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c4cfd-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4cfd-123">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c4cfd-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4cfd-124">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="c4cfd-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4cfd-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4cfd-125">See also</span></span>

- [<span data-ttu-id="c4cfd-126">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4cfd-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
