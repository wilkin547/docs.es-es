---
description: 'Más información sobre: ICorRuntimeHost:: Closeenum ((método)'
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
ms.openlocfilehash: 1fc18ff3e00f85a4f047417f880ec2b0e06496b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789728"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="e27c5-103">ICorRuntimeHost::CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="e27c5-103">ICorRuntimeHost::CloseEnum Method</span></span>

<span data-ttu-id="e27c5-104">Vuelve a establecer un enumerador de dominio al principio de la lista de dominios.</span><span class="sxs-lookup"><span data-stu-id="e27c5-104">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e27c5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e27c5-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e27c5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e27c5-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="e27c5-107">de Enumerador que se va a restablecer.</span><span class="sxs-lookup"><span data-stu-id="e27c5-107">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e27c5-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e27c5-108">Return Value</span></span>  
  
|<span data-ttu-id="e27c5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e27c5-109">HRESULT</span></span>|<span data-ttu-id="e27c5-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e27c5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e27c5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e27c5-111">S_OK</span></span>|<span data-ttu-id="e27c5-112">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e27c5-112">The operation was successful.</span></span>|  
|<span data-ttu-id="e27c5-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e27c5-113">S_FALSE</span></span>|<span data-ttu-id="e27c5-114">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="e27c5-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="e27c5-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e27c5-115">E_FAIL</span></span>|<span data-ttu-id="e27c5-116">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e27c5-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e27c5-117">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e27c5-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e27c5-118">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e27c5-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e27c5-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e27c5-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e27c5-120">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e27c5-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e27c5-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e27c5-121">Requirements</span></span>  

 <span data-ttu-id="e27c5-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e27c5-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e27c5-123">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e27c5-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e27c5-124">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e27c5-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e27c5-125">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e27c5-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e27c5-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e27c5-126">See also</span></span>

- [<span data-ttu-id="e27c5-127">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="e27c5-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="e27c5-128">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e27c5-128">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
