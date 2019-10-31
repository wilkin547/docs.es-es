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
ms.openlocfilehash: 2655151d34275b1b0fdc5d0903dd57fcea646014
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137312"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="d2f72-102">ICorDebugModule3::CreateReaderForInMemorySymbols (Método)</span><span class="sxs-lookup"><span data-stu-id="d2f72-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="d2f72-103">Crea un lector de símbolos de depuración para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="d2f72-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2f72-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2f72-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2f72-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2f72-105">Parameters</span></span>  
 <span data-ttu-id="d2f72-106">riid</span><span class="sxs-lookup"><span data-stu-id="d2f72-106">riid</span></span>  
 <span data-ttu-id="d2f72-107">de IID de la interfaz COM que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="d2f72-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="d2f72-108">Normalmente, se trata de una [interfaz ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d2f72-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="d2f72-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="d2f72-109">ppObj</span></span>  
 <span data-ttu-id="d2f72-110">enuncia Puntero a un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="d2f72-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2f72-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d2f72-111">Return Value</span></span>  
 <span data-ttu-id="d2f72-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2f72-112">S_OK</span></span>  
 <span data-ttu-id="d2f72-113">El lector se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d2f72-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="d2f72-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="d2f72-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="d2f72-115">El módulo no es un módulo dinámico o en memoria.</span><span class="sxs-lookup"><span data-stu-id="d2f72-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="d2f72-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d2f72-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="d2f72-117">La aplicación no ha proporcionado símbolos o no están disponibles todavía.</span><span class="sxs-lookup"><span data-stu-id="d2f72-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="d2f72-118">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="d2f72-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="d2f72-119">No se puede crear el lector.</span><span class="sxs-lookup"><span data-stu-id="d2f72-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2f72-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2f72-120">Remarks</span></span>  
 <span data-ttu-id="d2f72-121">Este método también se puede usar para crear un objeto de lector de símbolos para los módulos en memoria (no dinámicos), pero solo después de que los símbolos estén disponibles por primera vez (indicados por la devolución de llamada del [método updatemodulesymbols (](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="d2f72-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="d2f72-122">Este método devuelve una nueva instancia de lector cada vez que se llama (por ejemplo, [CComPtrBase:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span><span class="sxs-lookup"><span data-stu-id="d2f72-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="d2f72-123">Por consiguiente, el depurador debe almacenar en caché el resultado y solicitar una nueva instancia solo cuando los datos subyacentes puedan haber cambiado (es decir, cuando se recibe una devolución de llamada del [método loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="d2f72-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="d2f72-124">Los módulos dinámicos no tienen ningún símbolo disponible hasta que se carga el primer tipo (como indica la devolución de llamada del [método loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="d2f72-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2f72-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2f72-125">Requirements</span></span>  
 <span data-ttu-id="d2f72-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2f72-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2f72-127">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2f72-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2f72-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2f72-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2f72-129">**.NET Framework versiones:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="d2f72-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2f72-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2f72-130">See also</span></span>

- [<span data-ttu-id="d2f72-131">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2f72-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="d2f72-132">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2f72-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="d2f72-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d2f72-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
