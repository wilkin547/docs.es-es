---
title: ICorRuntimeHost::CloseEnum (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
ms.openlocfilehash: e2eddfab68e5c9e2ebffe2c96c9348f3cd799c7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127748"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="69fed-102">ICorRuntimeHost::CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="69fed-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="69fed-103">Vuelve a establecer un enumerador de dominio al principio de la lista de dominios.</span><span class="sxs-lookup"><span data-stu-id="69fed-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69fed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69fed-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69fed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69fed-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="69fed-106">de Enumerador que se va a restablecer.</span><span class="sxs-lookup"><span data-stu-id="69fed-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69fed-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="69fed-107">Return Value</span></span>  
  
|<span data-ttu-id="69fed-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="69fed-108">HRESULT</span></span>|<span data-ttu-id="69fed-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="69fed-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="69fed-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="69fed-110">S_OK</span></span>|<span data-ttu-id="69fed-111">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="69fed-111">The operation was successful.</span></span>|  
|<span data-ttu-id="69fed-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="69fed-112">S_FALSE</span></span>|<span data-ttu-id="69fed-113">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="69fed-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="69fed-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="69fed-114">E_FAIL</span></span>|<span data-ttu-id="69fed-115">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="69fed-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="69fed-116">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="69fed-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="69fed-117">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="69fed-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="69fed-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="69fed-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="69fed-119">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="69fed-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69fed-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69fed-120">Requirements</span></span>  
 <span data-ttu-id="69fed-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69fed-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69fed-122">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="69fed-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69fed-123">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="69fed-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69fed-124">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="69fed-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69fed-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="69fed-125">See also</span></span>

- [<span data-ttu-id="69fed-126">CorBindToRuntimeEx (función)</span><span class="sxs-lookup"><span data-stu-id="69fed-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="69fed-127">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69fed-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
