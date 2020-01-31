---
title: Interfaz ICorDebugType
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
ms.openlocfilehash: 8210e67f4bdd615ff65d9bd3474043fc45fd8883
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791259"
---
# <a name="icordebugtype-interface"></a>Interfaz ICorDebugType
Representa un tipo, ya sea básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumerateTypeParameters (método)](icordebugtype-enumeratetypeparameters-method.md)|Obtiene un puntero de interfaz a un ICorDebugTypeEnum que hace referencia a los parámetros de <xref:System.Type> genéricos de la clase a la que hace referencia este `ICorDebugType`.|  
|[GetBase (método)](icordebugtype-getbase-method.md)|Obtiene un puntero de interfaz a un `ICorDebugType` que hace referencia a la clase base de la clase a la que hace referencia este `ICorDebugType`, si existe uno.|  
|[GetClass (método)](icordebugtype-getclass-method.md)|Obtiene un puntero de interfaz a un ICorDebugClass que hace referencia al constructor con tipo de este `ICorDebugType`.|  
|[GetFirstTypeParameter (método)](icordebugtype-getfirsttypeparameter-method.md)|Obtiene un puntero de interfaz a un `ICorDebugType` que hace referencia al primer parámetro <xref:System.Type> genérico del constructor de la clase a la que hace referencia este `ICorDebugType`.|  
|[GetRank (método)](icordebugtype-getrank-method.md)|Obtiene el número de dimensiones de un tipo de matriz.|  
|[GetStaticFieldValue (método)](icordebugtype-getstaticfieldvalue-method.md)|Obtiene un puntero de interfaz a un ICorDebugValue que contiene el valor del campo estático al que hace referencia el token de campo especificado en el marco de pila especificado.|  
|[GetType (método)](icordebugtype-gettype-method.md)|Obtiene un valor de CorElementType que describe el tipo nativo del Common Language Runtime <xref:System.Type> al que hace referencia este `ICorDebugType`.|  
  
## <a name="remarks"></a>Notas  
 Si el tipo es genérico, `ICorDebugClass` representa el tipo sin instancia. La interfaz `ICorDebugType` representa un tipo genérico con instancias. Por ejemplo, la tabla hash\<K, V > se representará mediante `ICorDebugClass`, mientras que la tabla Hashtable\<Int32, > de cadena se representará mediante `ICorDebugType`.  
  
 Los tipos no genéricos están representados por `ICorDebugClass` y `ICorDebugType`. La última interfaz se presentó en la .NET Framework versión 2,0 para tratar con la creación de instancias de tipo.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
