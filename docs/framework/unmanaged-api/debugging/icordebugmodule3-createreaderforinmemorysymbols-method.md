---
title: ICorDebugModule3::CreateReaderForInMemorySymbols (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule3.CreateReaderForInMemorySymbols
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e404228cbc6efb81ed90c135358b1832ddcd8954
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "49373683"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="36cc2-102">ICorDebugModule3::CreateReaderForInMemorySymbols (Método)</span><span class="sxs-lookup"><span data-stu-id="36cc2-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="36cc2-103">Crea un lector de símbolos de depuración para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="36cc2-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36cc2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36cc2-104">Syntax</span></span>  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36cc2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36cc2-105">Parameters</span></span>  
 <span data-ttu-id="36cc2-106">riid</span><span class="sxs-lookup"><span data-stu-id="36cc2-106">riid</span></span>  
 <span data-ttu-id="36cc2-107">[in] IID de la interfaz COM para devolver.</span><span class="sxs-lookup"><span data-stu-id="36cc2-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="36cc2-108">Normalmente, esto es un [interfaz ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span><span class="sxs-lookup"><span data-stu-id="36cc2-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="36cc2-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="36cc2-109">ppObj</span></span>  
 <span data-ttu-id="36cc2-110">[out] Puntero a un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="36cc2-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36cc2-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="36cc2-111">Return Value</span></span>  
 <span data-ttu-id="36cc2-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="36cc2-112">S_OK</span></span>  
 <span data-ttu-id="36cc2-113">El lector se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="36cc2-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="36cc2-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="36cc2-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="36cc2-115">El módulo no es un módulo dinámico o en memoria.</span><span class="sxs-lookup"><span data-stu-id="36cc2-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="36cc2-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="36cc2-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="36cc2-117">Símbolos no se hayan especificado por la aplicación o todavía no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="36cc2-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="36cc2-118">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="36cc2-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="36cc2-119">No se puede crear el lector.</span><span class="sxs-lookup"><span data-stu-id="36cc2-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36cc2-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36cc2-120">Remarks</span></span>  
 <span data-ttu-id="36cc2-121">Este método también puede ser utilizado para crear un objeto de lector de símbolos para los módulos (no dinámicos) en memoria, pero solo después de que los símbolos primero están disponibles (indicado por el [UpdateModuleSymbols (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) devolución de llamada).</span><span class="sxs-lookup"><span data-stu-id="36cc2-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="36cc2-122">Este método devuelve una nueva instancia de lector cada vez que se llama (como [CComPtrBase:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span><span class="sxs-lookup"><span data-stu-id="36cc2-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="36cc2-123">Por lo tanto, el depurador debe almacenar en caché el resultado y solicitar una nueva instancia solo cuando pueden haber cambiado los datos subyacentes (es decir, cuando un [LoadClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) se recibe la devolución de llamada).</span><span class="sxs-lookup"><span data-stu-id="36cc2-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="36cc2-124">Módulos dinámicos no tiene ningún símbolo disponible hasta que se ha cargado el primer tipo (tal y como indica la [LoadClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) devolución de llamada).</span><span class="sxs-lookup"><span data-stu-id="36cc2-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36cc2-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36cc2-125">Requirements</span></span>  
 <span data-ttu-id="36cc2-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36cc2-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36cc2-127">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36cc2-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36cc2-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36cc2-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36cc2-129">**Versiones de .NET framework:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="36cc2-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36cc2-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="36cc2-130">See Also</span></span>  
 [<span data-ttu-id="36cc2-131">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36cc2-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="36cc2-132">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36cc2-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="36cc2-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="36cc2-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
