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
ms.openlocfilehash: 6596689af6533bb00f41b0d03805b3383ae8c3cc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792953"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="2c04d-102">ICorDebugModule3::CreateReaderForInMemorySymbols (Método)</span><span class="sxs-lookup"><span data-stu-id="2c04d-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="2c04d-103">Crea un lector de símbolos de depuración para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="2c04d-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c04d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c04d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c04d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2c04d-105">Parameters</span></span>  
 <span data-ttu-id="2c04d-106">riid</span><span class="sxs-lookup"><span data-stu-id="2c04d-106">riid</span></span>  
 <span data-ttu-id="2c04d-107">de IID de la interfaz COM que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="2c04d-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="2c04d-108">Normalmente, se trata de una [interfaz ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2c04d-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="2c04d-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="2c04d-109">ppObj</span></span>  
 <span data-ttu-id="2c04d-110">enuncia Puntero a un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="2c04d-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c04d-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2c04d-111">Return Value</span></span>  
 <span data-ttu-id="2c04d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c04d-112">S_OK</span></span>  
 <span data-ttu-id="2c04d-113">El lector se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c04d-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="2c04d-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="2c04d-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="2c04d-115">El módulo no es un módulo dinámico o en memoria.</span><span class="sxs-lookup"><span data-stu-id="2c04d-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="2c04d-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2c04d-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="2c04d-117">La aplicación no ha proporcionado símbolos o no están disponibles todavía.</span><span class="sxs-lookup"><span data-stu-id="2c04d-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="2c04d-118">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="2c04d-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="2c04d-119">No se puede crear el lector.</span><span class="sxs-lookup"><span data-stu-id="2c04d-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c04d-120">Notas</span><span class="sxs-lookup"><span data-stu-id="2c04d-120">Remarks</span></span>  
 <span data-ttu-id="2c04d-121">Este método también se puede usar para crear un objeto de lector de símbolos para los módulos en memoria (no dinámicos), pero solo después de que los símbolos estén disponibles por primera vez (indicados por la devolución de llamada del [método updatemodulesymbols (](icordebugmanagedcallback-updatemodulesymbols-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="2c04d-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="2c04d-122">Este método devuelve una nueva instancia de lector cada vez que se llama (por ejemplo, [CComPtrBase:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span><span class="sxs-lookup"><span data-stu-id="2c04d-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="2c04d-123">Por consiguiente, el depurador debe almacenar en caché el resultado y solicitar una nueva instancia solo cuando los datos subyacentes puedan haber cambiado (es decir, cuando se recibe una devolución de llamada del [método loadClass](icordebugmanagedcallback-loadclass-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="2c04d-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="2c04d-124">Los módulos dinámicos no tienen ningún símbolo disponible hasta que se carga el primer tipo (como indica la devolución de llamada del [método loadClass](icordebugmanagedcallback-loadclass-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="2c04d-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c04d-125">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2c04d-125">Requirements</span></span>  
 <span data-ttu-id="2c04d-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c04d-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c04d-127">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c04d-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c04d-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c04d-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c04d-129">**.NET Framework versiones:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="2c04d-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c04d-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c04d-130">See also</span></span>

- [<span data-ttu-id="2c04d-131">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c04d-131">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="2c04d-132">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c04d-132">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="2c04d-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2c04d-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
