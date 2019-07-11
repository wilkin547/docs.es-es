---
title: ICorRuntimeHost::GetDefaultDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe80050d7b513bce2660b81c5e4faa35b375f22b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780030"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="06e38-102">ICorRuntimeHost::GetDefaultDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="06e38-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="06e38-103">Obtiene un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> que representa el dominio predeterminado para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="06e38-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06e38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06e38-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06e38-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06e38-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="06e38-106">[out] Un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> a la <xref:System.AppDomain> instancia que representa el dominio de aplicación predeterminado para el proceso.</span><span class="sxs-lookup"><span data-stu-id="06e38-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="06e38-107">Este puntero es de tipo `IUnknown`, por lo que generalmente deberían llamar los llamadores `QueryInterface` para obtener un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="06e38-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06e38-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="06e38-108">Return Value</span></span>  
  
|<span data-ttu-id="06e38-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="06e38-109">HRESULT</span></span>|<span data-ttu-id="06e38-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="06e38-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06e38-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="06e38-111">S_OK</span></span>|<span data-ttu-id="06e38-112">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="06e38-112">The operation was successful.</span></span>|  
|<span data-ttu-id="06e38-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="06e38-113">S_FALSE</span></span>|<span data-ttu-id="06e38-114">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="06e38-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="06e38-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="06e38-115">E_FAIL</span></span>|<span data-ttu-id="06e38-116">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="06e38-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="06e38-117">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="06e38-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="06e38-118">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="06e38-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="06e38-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="06e38-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="06e38-120">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="06e38-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06e38-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06e38-121">Requirements</span></span>  
 <span data-ttu-id="06e38-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06e38-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06e38-123">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="06e38-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06e38-124">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06e38-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06e38-125">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="06e38-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06e38-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="06e38-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="06e38-127">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06e38-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
