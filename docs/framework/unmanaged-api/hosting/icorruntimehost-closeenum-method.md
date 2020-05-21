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
ms.openlocfilehash: a5a86df3ac1f50ca624490ad80a6fed903433436
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762375"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="126b6-102">ICorRuntimeHost::CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="126b6-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="126b6-103">Vuelve a establecer un enumerador de dominio al principio de la lista de dominios.</span><span class="sxs-lookup"><span data-stu-id="126b6-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="126b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="126b6-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="126b6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="126b6-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="126b6-106">de Enumerador que se va a restablecer.</span><span class="sxs-lookup"><span data-stu-id="126b6-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="126b6-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="126b6-107">Return Value</span></span>  
  
|<span data-ttu-id="126b6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="126b6-108">HRESULT</span></span>|<span data-ttu-id="126b6-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="126b6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="126b6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="126b6-110">S_OK</span></span>|<span data-ttu-id="126b6-111">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="126b6-111">The operation was successful.</span></span>|  
|<span data-ttu-id="126b6-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="126b6-112">S_FALSE</span></span>|<span data-ttu-id="126b6-113">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="126b6-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="126b6-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="126b6-114">E_FAIL</span></span>|<span data-ttu-id="126b6-115">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="126b6-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="126b6-116">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="126b6-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="126b6-117">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="126b6-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="126b6-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="126b6-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="126b6-119">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="126b6-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="126b6-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="126b6-120">Requirements</span></span>  
 <span data-ttu-id="126b6-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="126b6-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="126b6-122">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="126b6-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="126b6-123">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="126b6-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="126b6-124">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="126b6-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="126b6-125">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="126b6-125">See also</span></span>

- [<span data-ttu-id="126b6-126">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="126b6-126">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="126b6-127">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="126b6-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
