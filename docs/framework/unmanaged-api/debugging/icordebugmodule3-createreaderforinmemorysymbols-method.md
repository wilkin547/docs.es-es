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
ms.openlocfilehash: 44f4c59f95c28f9982d67875584e2f9803c0ed3b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709575"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a>ICorDebugModule3::CreateReaderForInMemorySymbols (Método)

Crea un lector de símbolos de depuración para un módulo dinámico.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a>Parámetros  

 riid  
 de IID de la interfaz COM que se va a devolver. Normalmente, se trata de una [interfaz ISymUnmanagedReader](../diagnostics/isymunmanagedreader-interface.md).  
  
 ppObj  
 enuncia Puntero a un puntero a la interfaz devuelta.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK  
 El lector se creó correctamente.  
  
 CORDBG_E_MODULE_LOADED_FROM_DISK  
 El módulo no es un módulo dinámico o en memoria.  
  
 CORDBG_E_SYMBOLS_NOT_AVAILABLE  
 La aplicación no ha proporcionado símbolos o no están disponibles todavía.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 No se puede crear el lector.  
  
## <a name="remarks"></a>Comentarios  

 Este método también se puede usar para crear un objeto de lector de símbolos para los módulos en memoria (no dinámicos), pero solo después de que los símbolos estén disponibles por primera vez (indicados por la devolución de llamada del [método updatemodulesymbols (](icordebugmanagedcallback-updatemodulesymbols-method.md) ).  
  
 Este método devuelve una nueva instancia de lector cada vez que se llama (por ejemplo, [CComPtrBase:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)). Por consiguiente, el depurador debe almacenar en caché el resultado y solicitar una nueva instancia solo cuando los datos subyacentes puedan haber cambiado (es decir, cuando se recibe una devolución de llamada del [método loadClass](icordebugmanagedcallback-loadclass-method.md) ).  
  
 Los módulos dinámicos no tienen ningún símbolo disponible hasta que se carga el primer tipo (como indica la devolución de llamada del [método loadClass](icordebugmanagedcallback-loadclass-method.md) ).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugRemoteTarget (Interfaz)](icordebugremotetarget-interface.md)
- [ICorDebug (Interfaz)](icordebug-interface.md)

- [Interfaces para depuración](debugging-interfaces.md)
