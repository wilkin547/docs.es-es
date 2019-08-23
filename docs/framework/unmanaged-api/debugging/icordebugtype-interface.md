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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b830af5d59c0eb177d815451ecedbdc14121aaad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964753"
---
# <a name="icordebugtype-interface"></a>Interfaz ICorDebugType
Representa un tipo, ya sea básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[EnumerateTypeParameters (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|Obtiene un puntero de interfaz a un ICorDebugTypeEnum que hace referencia <xref:System.Type> a los parámetros genéricos de la clase `ICorDebugType`a la que hace referencia.|  
|[GetBase (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|Obtiene un puntero de interfaz a `ICorDebugType` que hace referencia a la clase base de la clase a la `ICorDebugType`que hace referencia, si existe una.|  
|[GetClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|Obtiene un puntero de interfaz a un ICorDebugClass que hace referencia al constructor con tipo `ICorDebugType`de este.|  
|[GetFirstTypeParameter (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|Obtiene un puntero de interfaz a `ICorDebugType` un que hace referencia al <xref:System.Type> primer parámetro genérico del constructor de la `ICorDebugType`clase a la que hace referencia.|  
|[GetRank (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|Obtiene el número de dimensiones de un tipo de matriz.|  
|[GetStaticFieldValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|Obtiene un puntero de interfaz a un ICorDebugValue que contiene el valor del campo estático al que hace referencia el token de campo especificado en el marco de pila especificado.|  
|[GetType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|Obtiene un valor de CorElementType que describe el tipo nativo del Common Language Runtime <xref:System.Type> al que hace referencia `ICorDebugType`este.|  
  
## <a name="remarks"></a>Comentarios  
 Si el tipo es genérico, `ICorDebugClass` representa el tipo sin instancia. La `ICorDebugType` interfaz representa un tipo genérico con instancias. Por ejemplo, la\<tabla hash K, V > sería representada por\< `ICorDebugClass`, mientras que la tabla hash Int32, `ICorDebugType`String > se representaría mediante.  
  
 Los `ICorDebugClass` tipos no genéricos están representados `ICorDebugType`por y. La última interfaz se presentó en la .NET Framework versión 2,0 para tratar con la creación de instancias de tipo.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cordebug. idl, Cordebug. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
