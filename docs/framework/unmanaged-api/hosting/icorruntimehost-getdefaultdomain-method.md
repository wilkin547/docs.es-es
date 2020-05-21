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
ms.openlocfilehash: a23083777d0cd5965511f3689578a60220008420
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762235"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="a889a-102">ICorRuntimeHost::GetDefaultDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="a889a-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="a889a-103">Obtiene un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> que representa el dominio predeterminado para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="a889a-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a889a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a889a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a889a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a889a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="a889a-106">enuncia Puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> a la <xref:System.AppDomain> instancia de que representa el dominio de aplicación predeterminado para el proceso.</span><span class="sxs-lookup"><span data-stu-id="a889a-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="a889a-107">Este puntero tiene tipo `IUnknown` , por lo que los llamadores generalmente deben llamar `QueryInterface` a para obtener un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a889a-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a889a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a889a-108">Return Value</span></span>  
  
|<span data-ttu-id="a889a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a889a-109">HRESULT</span></span>|<span data-ttu-id="a889a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a889a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a889a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a889a-111">S_OK</span></span>|<span data-ttu-id="a889a-112">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a889a-112">The operation was successful.</span></span>|  
|<span data-ttu-id="a889a-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a889a-113">S_FALSE</span></span>|<span data-ttu-id="a889a-114">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="a889a-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="a889a-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a889a-115">E_FAIL</span></span>|<span data-ttu-id="a889a-116">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a889a-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a889a-117">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a889a-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="a889a-118">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a889a-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a889a-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a889a-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a889a-120">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a889a-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a889a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a889a-121">Requirements</span></span>  
 <span data-ttu-id="a889a-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a889a-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a889a-123">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a889a-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a889a-124">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a889a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a889a-125">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="a889a-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a889a-126">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="a889a-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="a889a-127">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a889a-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
