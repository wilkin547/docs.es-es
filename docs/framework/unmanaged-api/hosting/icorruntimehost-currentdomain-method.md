---
title: ICorRuntimeHost::CurrentDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CurrentDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CurrentDomain
helpviewer_keywords:
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
- CurrentDomain method [.NET Framework hosting]
ms.assetid: dd2afb38-675b-4c3c-a9f3-8ab3b133eb02
topic_type:
- apiref
ms.openlocfilehash: 33d56354a560949b2f451df9ef82d4f433951195
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715568"
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="56d1c-102">ICorRuntimeHost::CurrentDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="56d1c-102">ICorRuntimeHost::CurrentDomain Method</span></span>

<span data-ttu-id="56d1c-103">Obtiene un puntero de interfaz de tipo <xref:System.AppDomain?displayProperty=nameWithType> que representa el dominio cargado en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="56d1c-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56d1c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56d1c-104">Syntax</span></span>  
  
```cpp  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56d1c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56d1c-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="56d1c-106">enuncia Puntero de tipo <xref:System.AppDomain?displayProperty=nameWithType> que representa el dominio de aplicación actual del subproceso.</span><span class="sxs-lookup"><span data-stu-id="56d1c-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="56d1c-107">Este puntero tiene tipo `IUnknown` , por lo que los llamadores generalmente deben llamar `QueryInterface` a para obtener un puntero de tipo <xref:System._AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="56d1c-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56d1c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="56d1c-108">Return Value</span></span>  
  
|<span data-ttu-id="56d1c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56d1c-109">HRESULT</span></span>|<span data-ttu-id="56d1c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="56d1c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56d1c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="56d1c-111">S_OK</span></span>|<span data-ttu-id="56d1c-112">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="56d1c-112">The operation was successful.</span></span>|  
|<span data-ttu-id="56d1c-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="56d1c-113">S_FALSE</span></span>|<span data-ttu-id="56d1c-114">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="56d1c-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="56d1c-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="56d1c-115">E_FAIL</span></span>|<span data-ttu-id="56d1c-116">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="56d1c-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="56d1c-117">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="56d1c-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="56d1c-118">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="56d1c-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="56d1c-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="56d1c-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="56d1c-120">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="56d1c-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="56d1c-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56d1c-121">Requirements</span></span>  

 <span data-ttu-id="56d1c-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56d1c-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56d1c-123">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="56d1c-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56d1c-124">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="56d1c-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56d1c-125">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="56d1c-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56d1c-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56d1c-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="56d1c-127">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="56d1c-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
