---
description: 'Más información sobre: ICorDebugModule3:: Createreaderforinmemorysymbols ((método)'
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
ms.openlocfilehash: af037cc891e83f53fd94bad290f40286ed665e6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790781"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="f6deb-103">ICorDebugModule3::CreateReaderForInMemorySymbols (Método)</span><span class="sxs-lookup"><span data-stu-id="f6deb-103">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>

<span data-ttu-id="f6deb-104">Crea un lector de símbolos de depuración para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="f6deb-104">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6deb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6deb-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6deb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6deb-106">Parameters</span></span>  

 <span data-ttu-id="f6deb-107">riid</span><span class="sxs-lookup"><span data-stu-id="f6deb-107">riid</span></span>  
 <span data-ttu-id="f6deb-108">de IID de la interfaz COM que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="f6deb-108">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="f6deb-109">Normalmente, se trata de una [interfaz ISymUnmanagedReader](../diagnostics/isymunmanagedreader-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f6deb-109">Typically, this is an [ISymUnmanagedReader Interface](../diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="f6deb-110">ppObj</span><span class="sxs-lookup"><span data-stu-id="f6deb-110">ppObj</span></span>  
 <span data-ttu-id="f6deb-111">enuncia Puntero a un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="f6deb-111">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6deb-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f6deb-112">Return Value</span></span>  

 <span data-ttu-id="f6deb-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6deb-113">S_OK</span></span>  
 <span data-ttu-id="f6deb-114">El lector se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f6deb-114">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="f6deb-115">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="f6deb-115">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="f6deb-116">El módulo no es un módulo dinámico o en memoria.</span><span class="sxs-lookup"><span data-stu-id="f6deb-116">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="f6deb-117">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f6deb-117">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="f6deb-118">La aplicación no ha proporcionado símbolos o no están disponibles todavía.</span><span class="sxs-lookup"><span data-stu-id="f6deb-118">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="f6deb-119">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="f6deb-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="f6deb-120">No se puede crear el lector.</span><span class="sxs-lookup"><span data-stu-id="f6deb-120">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6deb-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f6deb-121">Remarks</span></span>  

 <span data-ttu-id="f6deb-122">Este método también se puede usar para crear un objeto de lector de símbolos para los módulos en memoria (no dinámicos), pero solo después de que los símbolos estén disponibles por primera vez (indicados por la devolución de llamada del [método updatemodulesymbols (](icordebugmanagedcallback-updatemodulesymbols-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="f6deb-122">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="f6deb-123">Este método devuelve una nueva instancia de lector cada vez que se llama (por ejemplo, [CComPtrBase:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span><span class="sxs-lookup"><span data-stu-id="f6deb-123">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="f6deb-124">Por consiguiente, el depurador debe almacenar en caché el resultado y solicitar una nueva instancia solo cuando los datos subyacentes puedan haber cambiado (es decir, cuando se recibe una devolución de llamada del [método loadClass](icordebugmanagedcallback-loadclass-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="f6deb-124">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="f6deb-125">Los módulos dinámicos no tienen ningún símbolo disponible hasta que se carga el primer tipo (como indica la devolución de llamada del [método loadClass](icordebugmanagedcallback-loadclass-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="f6deb-125">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6deb-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6deb-126">Requirements</span></span>  

 <span data-ttu-id="f6deb-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6deb-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6deb-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6deb-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6deb-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6deb-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6deb-130">**.NET Framework versiones:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="f6deb-130">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6deb-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6deb-131">See also</span></span>

- [<span data-ttu-id="f6deb-132">ICorDebugRemoteTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6deb-132">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="f6deb-133">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6deb-133">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="f6deb-134">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f6deb-134">Debugging Interfaces</span></span>](debugging-interfaces.md)
