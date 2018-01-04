---
title: "ICorDebugType::EnumerateTypeParameters (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.EnumerateTypeParameters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4b864b2b5fd4f2a6ed03218ce6e7b6f3bf62202
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>ICorDebugType::EnumerateTypeParameters (Método)
Obtiene un puntero de interfaz a ICorDebugTypeEnum que contiene el <xref:System.Type> parámetros de la clase al que hace referencia esta instancia de ICorDebugType.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppTyParEnum`  
 [out] Un puntero a la dirección de un `ICorDebugTypeEnum` que contiene los parámetros del tipo.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar `EnumerateTypeParameters` si el valor de CorElementType devuelto por [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) es ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_ PTR o ELEMENT_TYPE_FNPTR. El número de parámetros y su orden depende del tipo:  
  
-   ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE: el número de parámetros de tipo contenido en el `ICorDebugTypeEnum` que devuelve este método, dependerá del número de parámetros de tipo formales para la clase correspondiente. Por ejemplo, si el tipo es `class Dict<String,int32>`, a continuación, `EnumerateTypeParameters` devolverá un `ICorDebugTypeEnum` que contiene objetos que representan `String` y `int32` en secuencia.  
  
-   ELEMENT_TYPE_FNPTR: El número de parámetros de tipo contenido en el `ICorDebugTypeEnum` será a uno mayor que el número de argumentos aceptados por la función. El primer parámetro de tipo contenido en el `ICorDebugTypeEnum` es el tipo de valor devuelto para la función y los parámetros de tipo posteriores son parámetros de la función.  
  
-   ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR: se devolverá un parámetro de tipo. Por ejemplo, si el tipo es un tipo de matriz como `int32[]`,`EnumerateTypeParameters` devolverá un `ICorDebugTypeEnum` que contiene un objeto que representa `int32`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
