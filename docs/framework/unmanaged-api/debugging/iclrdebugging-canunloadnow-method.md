---
title: ICLRDebugging::CanUnloadNow (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebugging.CanUnloadNow Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type:
- apiref
ms.openlocfilehash: 4eb6682ac5a8b7788d97f752f249d85886fba0b6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111651"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="f94b5-102">ICLRDebugging::CanUnloadNow (Método)</span><span class="sxs-lookup"><span data-stu-id="f94b5-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="f94b5-103">Determina si una biblioteca proporcionada por una interfaz [ICLRDebuggingLibraryProvider (](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) todavía está en uso o se puede descargar.</span><span class="sxs-lookup"><span data-stu-id="f94b5-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f94b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f94b5-104">Syntax</span></span>  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f94b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f94b5-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="f94b5-106">de La dirección base de un módulo en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="f94b5-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f94b5-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f94b5-107">Return Value</span></span>  
 <span data-ttu-id="f94b5-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="f94b5-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f94b5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f94b5-109">HRESULT</span></span>|<span data-ttu-id="f94b5-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f94b5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f94b5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f94b5-111">S_OK</span></span>|<span data-ttu-id="f94b5-112">Se puede descargar el módulo al que hace referencia `hmodule`.</span><span class="sxs-lookup"><span data-stu-id="f94b5-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="f94b5-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f94b5-113">S_FALSE</span></span>|<span data-ttu-id="f94b5-114">El módulo al que hace referencia `hmodule` todavía está en uso.</span><span class="sxs-lookup"><span data-stu-id="f94b5-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="f94b5-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="f94b5-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="f94b5-116">El módulo indicado no es un módulo CLR.</span><span class="sxs-lookup"><span data-stu-id="f94b5-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f94b5-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="f94b5-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f94b5-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f94b5-118">Remarks</span></span>  
 <span data-ttu-id="f94b5-119">Este método comprueba si se han liberado todas las instancias de las interfaces de `ICorDebug*` y ningún subproceso está actualmente dentro de una llamada al método [ICLRDebugging:: openvirtualprocess (](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f94b5-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f94b5-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f94b5-120">Requirements</span></span>  
 <span data-ttu-id="f94b5-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f94b5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f94b5-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f94b5-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f94b5-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f94b5-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f94b5-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f94b5-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f94b5-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f94b5-125">See also</span></span>

- [<span data-ttu-id="f94b5-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f94b5-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f94b5-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="f94b5-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
