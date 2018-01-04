---
title: "ICorDebugModule3::CreateReaderForInMemorySymbols (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule3.CreateReaderForInMemorySymbols
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2838c6c1fe8641e343fac1a3efa82a39ee177abc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="33bac-102">ICorDebugModule3::CreateReaderForInMemorySymbols (Método)</span><span class="sxs-lookup"><span data-stu-id="33bac-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="33bac-103">Crea un lector de símbolos de depuración para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="33bac-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33bac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33bac-104">Syntax</span></span>  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33bac-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33bac-105">Parameters</span></span>  
 <span data-ttu-id="33bac-106">riid</span><span class="sxs-lookup"><span data-stu-id="33bac-106">riid</span></span>  
 <span data-ttu-id="33bac-107">[in] El IID de la interfaz COM para devolver.</span><span class="sxs-lookup"><span data-stu-id="33bac-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="33bac-108">Normalmente, esto es un [ISymUnmanagedReader (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span><span class="sxs-lookup"><span data-stu-id="33bac-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="33bac-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="33bac-109">ppObj</span></span>  
 <span data-ttu-id="33bac-110">[out] Puntero a un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="33bac-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33bac-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="33bac-111">Return Value</span></span>  
 <span data-ttu-id="33bac-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="33bac-112">S_OK</span></span>  
 <span data-ttu-id="33bac-113">El lector se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="33bac-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="33bac-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="33bac-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="33bac-115">El módulo no es un módulo dinámico o en memoria.</span><span class="sxs-lookup"><span data-stu-id="33bac-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="33bac-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="33bac-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="33bac-117">Símbolos no se ha proporcionado por la aplicación o todavía no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="33bac-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="33bac-118">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="33bac-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="33bac-119">No se puede crear el lector.</span><span class="sxs-lookup"><span data-stu-id="33bac-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33bac-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33bac-120">Remarks</span></span>  
 <span data-ttu-id="33bac-121">Este método también puede ser usado para crear un objeto de lector de símbolos para los módulos (no dinámicos) en memoria, pero solo después de que los símbolos que están disponibles en primer lugar (indicado por la [UpdateModuleSymbols (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) devolución de llamada).</span><span class="sxs-lookup"><span data-stu-id="33bac-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="33bac-122">Este método devuelve una nueva instancia de lector cada vez que se llama (como [CComPtrBase:: CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)).</span><span class="sxs-lookup"><span data-stu-id="33bac-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)).</span></span> <span data-ttu-id="33bac-123">Por lo tanto, el depurador debe almacenar en caché el resultado y solicitar una nueva instancia solo cuando pueden haber cambiado los datos subyacentes (es decir, cuando un [LoadClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) se recibe la devolución de llamada).</span><span class="sxs-lookup"><span data-stu-id="33bac-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="33bac-124">Módulos dinámicos no disponga de los símbolos disponibles hasta que se ha cargado el primer tipo (indicado por la [LoadClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) devolución de llamada).</span><span class="sxs-lookup"><span data-stu-id="33bac-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33bac-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33bac-125">Requirements</span></span>  
 <span data-ttu-id="33bac-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33bac-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33bac-127">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33bac-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33bac-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33bac-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33bac-129">**Versiones de .NET framework:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="33bac-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33bac-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="33bac-130">See Also</span></span>  
 [<span data-ttu-id="33bac-131">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33bac-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="33bac-132">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33bac-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="33bac-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="33bac-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
