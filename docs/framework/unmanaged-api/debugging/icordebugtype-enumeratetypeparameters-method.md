---
title: ICorDebugType::EnumerateTypeParameters (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8fa39a54437e60737aa052c495f58422bc0d3fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946242"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>ICorDebugType::EnumerateTypeParameters (Método)
Obtiene un puntero de interfaz a ICorDebugTypeEnum que contiene el <xref:System.Type> parámetros de la clase que se hace referencia a esta instancia de ICorDebugType.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppTyParEnum`  
 [out] Un puntero a la dirección de un `ICorDebugTypeEnum` que contiene los parámetros del tipo.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar `EnumerateTypeParameters` si el valor CorElementType devuelto por [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) es ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_ PTR o ELEMENT_TYPE_FNPTR. El número de parámetros y su orden depende del tipo:  
  
- ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE: El número de parámetros de tipo contenido en el `ICorDebugTypeEnum` que devuelve este método, dependerá del número de parámetros de tipo formal para la clase correspondiente. Por ejemplo, si el tipo es `class Dict<String,int32>`, a continuación, `EnumerateTypeParameters` devolverá un `ICorDebugTypeEnum` que contiene objetos que representan `String` y `int32` en secuencia.  
  
- ELEMENT_TYPE_FNPTR: El número de parámetros de tipo contenido en el `ICorDebugTypeEnum` es uno mayor que el número de argumentos aceptados por la función. El primer parámetro de tipo contenido en el `ICorDebugTypeEnum` es el tipo de valor devuelto para la función y los parámetros de tipo posteriores son parámetros de la función.  
  
- ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR: Un parámetro de tipo se devolverá. Por ejemplo, si el tipo es un tipo de matriz como `int32[]`,`EnumerateTypeParameters` devolverá un `ICorDebugTypeEnum` que contiene un objeto que representa `int32`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
