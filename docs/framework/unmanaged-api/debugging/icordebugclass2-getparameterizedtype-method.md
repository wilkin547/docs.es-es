---
title: "ICorDebugClass2::GetParameterizedType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2.GetParameterizedType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9cbb755bd8f52482f7eece6e9d236f29cadc419
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass2getparameterizedtype-method"></a>ICorDebugClass2::GetParameterizedType (Método)
Obtiene la declaración de tipo para esta clase.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `elementType`  
 [in] Un valor de la enumeración CorElementType que especifica el tipo de elemento para esta clase: establezca este valor en ELEMENT_TYPE_VALUETYPE si ICorDebugClass2 representa un tipo de valor. Establezca este valor en ELEMENT_TYPE_CLASS si este `ICorDebugClass2` representa un tipo complejo.  
  
 `nTypeArgs`  
 [in] El número de parámetros de tipo, si el tipo es genérico. El número de parámetros de tipo (si existe) debe coincidir con el número necesario por la clase.  
  
 `ppTypeArgs`  
 [in] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un parámetro de tipo. Si la clase es no genérica, este valor es null.  
  
 `ppType`  
 [out] Un puntero a la dirección de un `ICorDebugType` objeto que representa la declaración de tipos. Este objeto es equivalente a un <xref:System.Type> objeto en código administrado.  
  
## <a name="remarks"></a>Comentarios  
 Si la clase es no genérica, es decir, si no tiene ningún parámetro de tipo, `GetParameterizedType` simplemente obtiene el objeto de tipo en tiempo de ejecución correspondiente a la clase. El `elementType` parámetro debe establecerse en el tipo de elemento correcto para la clase: ELEMENT_TYPE_VALUETYPE si la clase es un tipo de valor; en caso contrario, ELEMENT_TYPE_CLASS.  
  
 Si la clase acepta parámetros de tipo (por ejemplo, `ArrayList<T>`), puede usar `GetParameterizedType` para construir un objeto de tipo para una instancia de un tipo como `ArrayList<int>`.  
  
## <a name="background-information"></a>Información general  
 En las versiones 1.0 y 1.1 de .NET Framework, todos los tipos en los metadatos pudieron asignarse directamente a un tipo en el proceso en ejecución. Por lo tanto, un tipo de metadatos y un tipo en tiempo de ejecución tenían una única representación de los procesos en ejecución. Sin embargo, un tipo genérico en los metadatos puede asignarse a muchas de las distintas instancias del tipo en el proceso en ejecución. Por ejemplo, el tipo de metadatos `SortedList<K,V>` puede asignar a `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, y así sucesivamente. Por lo tanto, necesita una manera de controlar la creación de instancias de tipo.  
  
 La versión 2.0 de .NET Framework presenta la `ICorDebugType` interfaz. Para un tipo genérico, un `ICorDebugClass` o `ICorDebugClass2` objeto representa el tipo sin instancias (`SortedList<K,V>`) y un `ICorDebugType` representa los distintos tipos de instancias de objeto. Dado un `ICorDebugClass` o `ICorDebugClass2` objeto, puede crear un `ICorDebugType` objeto para la creación de instancias mediante una llamada a la `ICorDebugClass2::GetParameterizedType` método. También puede crear un `ICorDebugType` objeto para un tipo simple, como Int32, o para un tipo no genérico.  
  
 La introducción de la `ICorDebugType` que represente la noción de tiempo de ejecución de un tipo de objeto tiene un efecto dominó a lo largo de la API. Funciones que realizó anteriormente una `ICorDebugClass` o `ICorDebugClass2` objeto o incluso un `CorElementType` valor están generalizados para tomar un `ICorDebugType` objeto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
