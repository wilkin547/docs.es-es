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
ms.openlocfilehash: d3748621474373fee8248496d48414ff67c699d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715703"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="8ef7b-102">ICorRuntimeHost::CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="8ef7b-102">ICorRuntimeHost::CloseEnum Method</span></span>

<span data-ttu-id="8ef7b-103">Vuelve a establecer un enumerador de dominio al principio de la lista de dominios.</span><span class="sxs-lookup"><span data-stu-id="8ef7b-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ef7b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ef7b-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ef7b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8ef7b-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="8ef7b-106">de Enumerador que se va a restablecer.</span><span class="sxs-lookup"><span data-stu-id="8ef7b-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ef7b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8ef7b-107">Return Value</span></span>  
  
|<span data-ttu-id="8ef7b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ef7b-108">HRESULT</span></span>|<span data-ttu-id="8ef7b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ef7b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ef7b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ef7b-110">S_OK</span></span>|<span data-ttu-id="8ef7b-111">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8ef7b-111">The operation was successful.</span></span>|  
|<span data-ttu-id="8ef7b-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8ef7b-112">S_FALSE</span></span>|<span data-ttu-id="8ef7b-113">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="8ef7b-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="8ef7b-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ef7b-114">E_FAIL</span></span>|<span data-ttu-id="8ef7b-115">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="8ef7b-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="8ef7b-116">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8ef7b-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="8ef7b-117">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8ef7b-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8ef7b-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ef7b-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ef7b-119">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8ef7b-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ef7b-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ef7b-120">Requirements</span></span>  

 <span data-ttu-id="8ef7b-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ef7b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ef7b-122">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8ef7b-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ef7b-123">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ef7b-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ef7b-124">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="8ef7b-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef7b-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ef7b-125">See also</span></span>

- [<span data-ttu-id="8ef7b-126">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="8ef7b-126">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="8ef7b-127">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8ef7b-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
