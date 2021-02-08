---
description: 'Más información sobre: ICorDebugType (interfaz)'
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
ms.openlocfilehash: 4cd668263906ef21e1bb665795425ca3a239c2bd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800895"
---
# <a name="icordebugtype-interface"></a>Interfaz ICorDebugType

Representa un tipo, ya sea básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnumerateTypeParameters](icordebugtype-enumeratetypeparameters-method.md)|Obtiene un puntero de interfaz a un ICorDebugTypeEnum que hace referencia a los parámetros genéricos <xref:System.Type> de la clase a la que hace referencia `ICorDebugType` .|  
|[Método GetBase](icordebugtype-getbase-method.md)|Obtiene un puntero de interfaz a `ICorDebugType` que hace referencia a la clase base de la clase a la que hace referencia `ICorDebugType` , si existe una.|  
|[Método GetClass](icordebugtype-getclass-method.md)|Obtiene un puntero de interfaz a un ICorDebugClass que hace referencia al constructor con tipo de este `ICorDebugType` .|  
|[Método GetFirstTypeParameter](icordebugtype-getfirsttypeparameter-method.md)|Obtiene un puntero de interfaz a un `ICorDebugType` que hace referencia al primer parámetro genérico del <xref:System.Type> constructor de la clase a la que hace referencia `ICorDebugType` .|  
|[Método GetRank](icordebugtype-getrank-method.md)|Obtiene el número de dimensiones de un tipo de matriz.|  
|[Método GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md)|Obtiene un puntero de interfaz a un ICorDebugValue que contiene el valor del campo estático al que hace referencia el token de campo especificado en el marco de pila especificado.|  
|[Método GetType](icordebugtype-gettype-method.md)|Obtiene un valor de CorElementType que describe el tipo nativo del Common Language Runtime <xref:System.Type> al que hace referencia este `ICorDebugType` .|  
  
## <a name="remarks"></a>Observaciones  

 Si el tipo es genérico, `ICorDebugClass` representa el tipo sin instancia. La `ICorDebugType` interfaz representa un tipo genérico con instancias. Por ejemplo, la tabla hash \<K, V> se representará mediante `ICorDebugClass` , mientras que la tabla hash \<Int32, String> se representará mediante `ICorDebugType` .  
  
 Los tipos no genéricos están representados por `ICorDebugClass` y `ICorDebugType` . La última interfaz se presentó en la .NET Framework versión 2,0 para tratar con la creación de instancias de tipo.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
