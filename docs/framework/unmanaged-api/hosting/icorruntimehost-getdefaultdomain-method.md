---
description: 'Más información sobre: ICorRuntimeHost:: Getdefaultdomain ((método)'
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
ms.openlocfilehash: 53be5e3db7bec396743edc728942ad54efc0ec16
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753827"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="b45b1-103">ICorRuntimeHost::GetDefaultDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="b45b1-103">ICorRuntimeHost::GetDefaultDomain Method</span></span>

<span data-ttu-id="b45b1-104">Obtiene un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> que representa el dominio predeterminado para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="b45b1-104">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b45b1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b45b1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b45b1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b45b1-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="b45b1-107">enuncia Puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> a la <xref:System.AppDomain> instancia de que representa el dominio de aplicación predeterminado para el proceso.</span><span class="sxs-lookup"><span data-stu-id="b45b1-107">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="b45b1-108">Este puntero tiene tipo `IUnknown` , por lo que los llamadores generalmente deben llamar `QueryInterface` a para obtener un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="b45b1-108">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b45b1-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b45b1-109">Return Value</span></span>  
  
|<span data-ttu-id="b45b1-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b45b1-110">HRESULT</span></span>|<span data-ttu-id="b45b1-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b45b1-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b45b1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b45b1-112">S_OK</span></span>|<span data-ttu-id="b45b1-113">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="b45b1-113">The operation was successful.</span></span>|  
|<span data-ttu-id="b45b1-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b45b1-114">S_FALSE</span></span>|<span data-ttu-id="b45b1-115">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="b45b1-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="b45b1-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b45b1-116">E_FAIL</span></span>|<span data-ttu-id="b45b1-117">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="b45b1-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="b45b1-118">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b45b1-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="b45b1-119">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b45b1-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b45b1-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b45b1-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b45b1-121">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b45b1-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b45b1-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b45b1-122">Requirements</span></span>  

 <span data-ttu-id="b45b1-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b45b1-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b45b1-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b45b1-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b45b1-125">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b45b1-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b45b1-126">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="b45b1-126">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b45b1-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="b45b1-127">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="b45b1-128">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b45b1-128">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
