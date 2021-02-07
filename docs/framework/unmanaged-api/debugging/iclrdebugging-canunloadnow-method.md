---
description: 'Más información sobre: ICLRDebugging:: Canunloadnow ((método)'
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
ms.openlocfilehash: 537494fe862c58aa8a8768dd5ce2abc8ca94f87d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723379"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="89503-103">ICLRDebugging::CanUnloadNow (Método)</span><span class="sxs-lookup"><span data-stu-id="89503-103">ICLRDebugging::CanUnloadNow Method</span></span>

<span data-ttu-id="89503-104">Determina si una biblioteca proporcionada por una interfaz [ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md) todavía está en uso o se puede descargar.</span><span class="sxs-lookup"><span data-stu-id="89503-104">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89503-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89503-105">Syntax</span></span>  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89503-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89503-106">Parameters</span></span>  

 `hmodule`  
 <span data-ttu-id="89503-107">de La dirección base de un módulo en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="89503-107">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89503-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="89503-108">Return Value</span></span>  

 <span data-ttu-id="89503-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="89503-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="89503-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89503-110">HRESULT</span></span>|<span data-ttu-id="89503-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="89503-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89503-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="89503-112">S_OK</span></span>|<span data-ttu-id="89503-113">Se puede descargar el módulo al que hace referencia `hmodule` .</span><span class="sxs-lookup"><span data-stu-id="89503-113">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="89503-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="89503-114">S_FALSE</span></span>|<span data-ttu-id="89503-115">El módulo al que hace referencia `hmodule` está todavía en uso.</span><span class="sxs-lookup"><span data-stu-id="89503-115">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="89503-116">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="89503-116">COR_E_NOT_CLR</span></span>|<span data-ttu-id="89503-117">El módulo indicado no es un módulo CLR.</span><span class="sxs-lookup"><span data-stu-id="89503-117">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="89503-118">Excepciones</span><span class="sxs-lookup"><span data-stu-id="89503-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89503-119">Notas</span><span class="sxs-lookup"><span data-stu-id="89503-119">Remarks</span></span>  

 <span data-ttu-id="89503-120">Este método comprueba si se han liberado todas las instancias de las `ICorDebug*` interfaces y ningún subproceso está actualmente dentro de una llamada al método [ICLRDebugging:: openvirtualprocess (](iclrdebugging-openvirtualprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="89503-120">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89503-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89503-121">Requirements</span></span>  

 <span data-ttu-id="89503-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89503-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89503-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89503-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89503-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89503-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89503-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89503-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89503-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="89503-126">See also</span></span>

- [<span data-ttu-id="89503-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="89503-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="89503-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="89503-128">Debugging</span></span>](index.md)
