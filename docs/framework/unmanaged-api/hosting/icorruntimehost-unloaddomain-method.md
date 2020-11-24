---
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
ms.openlocfilehash: 94c84d876e19ec2ff7baba5a5a7420eec68d58c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690114"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="9b625-102">ICorRuntimeHost::UnloadDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="9b625-102">ICorRuntimeHost::UnloadDomain Method</span></span>

<span data-ttu-id="9b625-103">Descarga el dominio de aplicación especificado del proceso actual.</span><span class="sxs-lookup"><span data-stu-id="9b625-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b625-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b625-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b625-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b625-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="9b625-106">de Puntero de tipo <xref:System._AppDomain?displayProperty=nameWithType> que representa el dominio que se va a descargar.</span><span class="sxs-lookup"><span data-stu-id="9b625-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b625-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9b625-107">Return Value</span></span>  
  
|<span data-ttu-id="9b625-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b625-108">HRESULT</span></span>|<span data-ttu-id="9b625-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b625-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b625-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b625-110">S_OK</span></span>|<span data-ttu-id="9b625-111">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b625-111">The operation was successful.</span></span>|  
|<span data-ttu-id="9b625-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9b625-112">S_FALSE</span></span>|<span data-ttu-id="9b625-113">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="9b625-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="9b625-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b625-114">E_FAIL</span></span>|<span data-ttu-id="9b625-115">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="9b625-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="9b625-116">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="9b625-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="9b625-117">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9b625-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9b625-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b625-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b625-119">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b625-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b625-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b625-120">Requirements</span></span>  

 <span data-ttu-id="9b625-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b625-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b625-122">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9b625-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b625-123">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b625-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b625-124">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="9b625-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b625-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b625-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="9b625-126">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b625-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
