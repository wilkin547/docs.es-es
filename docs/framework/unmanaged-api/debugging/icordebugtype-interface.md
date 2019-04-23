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
ms.openlocfilehash: 74863af1096f8600b8095e593c1f3c820c512e9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166808"
---
# <a name="icordebugtype-interface"></a>Interfaz ICorDebugType
Representa un tipo, básico o complejo (que es, definido por el usuario). Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumerateTypeParameters (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|Obtiene un puntero de interfaz a ICorDebugTypeEnum que hace referencia el tipo genérico <xref:System.Type> parámetros de la clase que hace referencia esta `ICorDebugType`.|  
|[GetBase (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|Obtiene un puntero de interfaz a un `ICorDebugType` que hace referencia a la clase base de la clase que hace referencia esta `ICorDebugType`, si existe alguno.|  
|[GetClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|Obtiene un puntero de interfaz a ICorDebugClass que hace referencia al constructor con tipo de este `ICorDebugType`.|  
|[GetFirstTypeParameter (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|Obtiene un puntero de interfaz a un `ICorDebugType` que hace referencia a la primera genérica <xref:System.Type> parámetro para el constructor de la clase que hace referencia esta `ICorDebugType`.|  
|[GetRank (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|Obtiene el número de dimensiones en un tipo de matriz.|  
|[GetStaticFieldValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|Obtiene un puntero de interfaz al ICorDebugValue que contiene el valor del campo estático al que hace referencia el campo especificado token en el marco de pila especificado.|  
|[GetType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|Obtiene un valor de CorElementType que describe el tipo nativo de common language runtime <xref:System.Type> hace referencia este `ICorDebugType`.|  
  
## <a name="remarks"></a>Comentarios  
 Si el tipo es genérico, `ICorDebugClass` representa el tipo sin instancias. El `ICorDebugType` interfaz representa un tipo genérico con instancias. Por ejemplo, Hashtable\<K, V > se representaría mediante `ICorDebugClass`, mientras que Hashtable\<Int32, String > se representaría mediante `ICorDebugType`.  
  
 Los tipos no genéricos se representan mediante dos `ICorDebugClass` y `ICorDebugType`. La última interfaz se introdujo en la versión 2.0 de .NET Framework para tratar con la creación de instancias de tipo.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
