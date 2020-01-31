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
ms.openlocfilehash: b2c381d093069f5ee86be1b19d75f5c2d69ad9fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791311"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>ICorDebugType::EnumerateTypeParameters (Método)
Obtiene un puntero de interfaz a un ICorDebugTypeEnum que contiene los parámetros de <xref:System.Type> de la clase a la que hace referencia esta ICorDebugType.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppTyParEnum`  
 enuncia Puntero a la dirección de una `ICorDebugTypeEnum` que contiene los parámetros del tipo.  
  
## <a name="remarks"></a>Notas  
 Puede usar `EnumerateTypeParameters` si el valor de CorElementType devuelto por [ICorDebugType:: GetType](icordebugtype-gettype-method.md) es ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR o ELEMENT_TYPE_FNPTR. El número de parámetros y su orden dependen del tipo:  
  
- ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE: el número de parámetros de tipo contenidos en el `ICorDebugTypeEnum` que devuelve este método dependerá del número de parámetros de tipo formal de la clase correspondiente. Por ejemplo, si el tipo es `class Dict<String,int32>`, `EnumerateTypeParameters` devolverá un `ICorDebugTypeEnum` que contiene objetos que representan `String` y `int32` en la secuencia.  
  
- ELEMENT_TYPE_FNPTR: el número de parámetros de tipo contenidos en el `ICorDebugTypeEnum` será uno mayor que el número de argumentos aceptados por la función. El primer parámetro de tipo contenido en la `ICorDebugTypeEnum` es el tipo de valor devuelto para la función y los parámetros de tipo subsiguientes son los parámetros de la función.  
  
- ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR: se devolverá un parámetro de tipo. Por ejemplo, si el tipo es un tipo de matriz, como `int32[]`,`EnumerateTypeParameters` devolverá un `ICorDebugTypeEnum` que contiene un objeto que representa `int32`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
