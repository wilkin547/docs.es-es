---
title: ICorDebugClass2::GetParameterizedType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
ms.openlocfilehash: 139181975d16c2cdacec10ed646cfc2b8fb31a20
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717999"
---
# <a name="icordebugclass2getparameterizedtype-method"></a>ICorDebugClass2::GetParameterizedType (Método)

Obtiene la declaración de tipos para esta clase.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `elementType`  
 de Un valor de la enumeración CorElementType que especifica el tipo de elemento para esta clase: establezca este valor en ELEMENT_TYPE_VALUETYPE si este ICorDebugClass2 representa un tipo de valor. Establezca este valor en ELEMENT_TYPE_CLASS si este `ICorDebugClass2` representa un tipo complejo.  
  
 `nTypeArgs`  
 de El número de parámetros de tipo, si el tipo es genérico. El número de parámetros de tipo (si existen) debe coincidir con el número requerido por la clase.  
  
 `ppTypeArgs`  
 de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un parámetro de tipo. Si la clase no es genérica, este valor es NULL.  
  
 `ppType`  
 enuncia Puntero a la dirección de un `ICorDebugType` objeto que representa la declaración de tipos. Este objeto es equivalente a un <xref:System.Type> objeto en código administrado.  
  
## <a name="remarks"></a>Comentarios  

 Si la clase no es genérica, es decir, si no tiene parámetros de tipo, `GetParameterizedType` simplemente obtiene el objeto de tipo en tiempo de ejecución correspondiente a la clase. El `elementType` parámetro debe establecerse en el tipo de elemento correcto para la clase: ELEMENT_TYPE_VALUETYPE si la clase es un tipo de valor; de lo contrario, ELEMENT_TYPE_CLASS.  
  
 Si la clase acepta parámetros de tipo (por ejemplo, `ArrayList<T>` ), puede usar `GetParameterizedType` para construir un objeto de tipo para un tipo con instancias como `ArrayList<int>` .  
  
## <a name="background-information"></a>Información general  

 En las versiones .NET Framework 1,0 y 1,1, cada tipo de los metadatos se puede asignar directamente a un tipo en el proceso en ejecución. Por lo tanto, un tipo de metadatos y un tipo en tiempo de ejecución tenían una única representación en el proceso en ejecución. Sin embargo, un tipo genérico en los metadatos se puede asignar a muchas instancias diferentes del tipo en el proceso en ejecución. Por ejemplo, el tipo de metadatos `SortedList<K,V>` se puede asignar a `SortedList<String, EmployeeRecord>` , `SortedList<Int32, String>` , `SortedList<String,Array<Int32>>` , etc. Por lo tanto, necesita una manera de controlar la creación de instancias de tipos.  
  
 La versión 2,0 de .NET Framework presenta la `ICorDebugType` interfaz. Para un tipo genérico, un `ICorDebugClass` `ICorDebugClass2` objeto o representa el tipo sin instancia ( `SortedList<K,V>` ) y un `ICorDebugType` objeto representa los distintos tipos con instancias. Dado un `ICorDebugClass` `ICorDebugClass2` objeto o, puede crear un `ICorDebugType` objeto para cualquier instancia de mediante una llamada al `ICorDebugClass2::GetParameterizedType` método. También puede crear un `ICorDebugType` objeto para un tipo simple, como Int32, o para un tipo no genérico.  
  
 La introducción del `ICorDebugType` objeto para representar la noción en tiempo de ejecución de un tipo tiene un efecto de rizo en toda la API. Las funciones que anteriormente tomaban un `ICorDebugClass` `ICorDebugClass2` objeto o o incluso un `CorElementType` valor se generalizan para tomar un `ICorDebugType` objeto.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
