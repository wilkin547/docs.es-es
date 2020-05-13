---
title: ICorDebugILFrame3::GetReturnValueForILOffset (Método)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
ms.openlocfilehash: f6a54ab9efa7ca97bcdb64afcde8812f2b5e44e9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210077"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>ICorDebugILFrame3::GetReturnValueForILOffset (Método)
Obtiene un objeto "ICorDebugValue" que encapsula el valor devuelto de una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ILOffset`  
 Desplazamiento IL. Consulte la sección Comentarios.  
  
 `ppReturnValue`  
 Puntero a la dirección de un objeto de interfaz "ICorDebugValue" que proporciona información sobre el valor devuelto de una llamada de función.  
  
## <a name="remarks"></a>Observaciones  
 Este método se usa junto con el método [ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) para obtener el valor devuelto de un método. Resulta especialmente útil en el caso de los métodos cuyos valores devueltos se omiten, como en los dos ejemplos de código siguientes. El primer ejemplo llama al método <xref:System.Int32.TryParse%2A?displayProperty=nameWithType>, pero omite el valor devuelto.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 El segundo ejemplo muestra un problema mucho más común de depuración. Dado que se usa un método como argumento en una llamada al método, solo se puede tener acceso al valor devuelto cuando el depurador recorre el método llamado. En muchos casos, especialmente cuando el método al que se llama se define en una biblioteca externa, eso no es posible.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 Si pasa el método [ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) un desplazamiento Il a un sitio de llamada de función, devuelve uno o varios desplazamientos nativos. El depurador puede establecer puntos de interrupción en estos desplazamientos nativos en la función. Cuando el depurador llega a uno de los puntos de interrupción, podrá pasar el mismo desplazamiento IL que pasó a este método para obtener el valor devuelto. A continuación, el depurador debe borrar todos los puntos de interrupción que estableció.  
  
> [!WARNING]
> El método y los métodos [ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) `ICorDebugILFrame3::GetReturnValueForILOffset` permiten obtener información del valor devuelto solo para los tipos de referencia. La recuperación de información de valor devuelto de tipos de valor (es decir, todos los tipos derivados de <xref:System.ValueType>) no se admite.  
  
 El desplazamiento IL especificado por el `ILOffset` parámetro debe estar en un sitio de llamada de función y el código depurado debe detenerse en un punto de interrupción establecido en el desplazamiento nativo devuelto por el método [ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) para el mismo desplazamiento Il. Si el código que se está depurando no se detiene en la ubicación correcta para el desplazamiento IL especificado, se producirá un error en la API.  
  
 Si la llamada de función no devuelve un valor, se producirá un error en la API.  
  
 El método `ICorDebugILFrame3::GetReturnValueForILOffset` solo está disponible en los sistemas basados en x86 y AMD64.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md)
- [ICorDebugILFrame3 (Interfaz)](icordebugilframe3-interface.md)
