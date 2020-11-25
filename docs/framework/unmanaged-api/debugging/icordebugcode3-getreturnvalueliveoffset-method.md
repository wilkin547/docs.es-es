---
title: ICorDebugCode3::GetReturnValueLiveOffset (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
ms.openlocfilehash: 6153ebf24ae939a50d71cad2d4323090aa905851
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720820"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a>ICorDebugCode3::GetReturnValueLiveOffset (Método)

Para un desplazamiento de IL especificado, obtiene los desplazamientos nativos donde se debe colocar un punto de interrupción de modo que el depurador pueda obtener el valor devuelto de una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,
    [out] ULONG32 *pFetched,
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ILoffset`  
 Desplazamiento IL. Debe ser un sitio de la llamada de función o la llamada de función generará un error.  
  
 `bufferSize`  
 Número de bytes disponible para almacenar `pOffsets`.  
  
 `pFetched`  
 Un puntero al número de desplazamientos realmente devueltos. Generalmente, su valor es 1, pero una sola instrucción IL puede asignarse a varias instrucciones de ensamblado `CALL`.  
  
 `pOffsets`  
 Matriz de desplazamientos nativos. Normalmente, `pOffsets` contiene un único desplazamiento, aunque una sola instrucción IL puede asociar varios mapas a varias instrucciones de ensamblado `CALL`.  
  
## <a name="remarks"></a>Comentarios  

 Este método se usa junto con el método [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) para obtener el valor devuelto de un método que devuelve un tipo de referencia. Pasar un desplazamiento IL a un sitio de la llamada de función a este método devuelve uno o varios desplazamientos nativos. El depurador puede establecer puntos de interrupción en estos desplazamientos nativos en la función. Cuando el depurador llega a uno de los puntos de interrupción, puede pasar el mismo desplazamiento IL que pasó a este método al método [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) para obtener el valor devuelto. A continuación, el depurador debe borrar todos los puntos de interrupción que estableció.  
  
> [!WARNING]
> Los `ICorDebugCode3::GetReturnValueLiveOffset` métodos y [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) permiten obtener información del valor devuelto solo para los tipos de referencia. La recuperación de información de valor devuelto de tipos de valor (es decir, todos los tipos derivados de <xref:System.ValueType>) no se admite.  
  
 La función devuelve los valores `HRESULT` mostrados en la tabla siguiente.  
  
|Valor de `HRESULT`|Descripción|  
|---------------------|-----------------|  
|`S_OK`|Correcto.|  
|`CORDBG_E_INVALID_OPCODE`|El sitio de desplazamiento IL dado no es una instrucción de llamada o la función devuelve `void`.|  
|`CORDBG_E_UNSUPPORTED`|El desplazamiento IL dado es una llamada correcta, pero el tipo de valor devuelto no se admite para obtener un valor devuelto.|  
  
 El método `ICorDebugCode3::GetReturnValueLiveOffset` solo está disponible en los sistemas basados en x86 y AMD64.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [ICorDebugCode3 (Interfaz)](icordebugcode3-interface.md)
