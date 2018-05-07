---
title: ICorDebugClass Interfaz1
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bec35babec96da5ca5d527b19f853b4ce1c384e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugclass-interface1"></a>ICorDebugClass Interfaz1
Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetModule (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Obtiene el módulo que define esta clase.|  
|[GetStaticFieldValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|Obtiene el valor del campo estático especificado.|  
|[GetToken (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|Obtiene el `TypeDef` símbolo (token) de metadatos para esta clase.|  
  
## <a name="remarks"></a>Comentarios  
 El `ICorDebugClass` interfaz representa un tipo genérico sin instancias. ICorDebugType (interfaz) representa un tipo genérico con instancias. Por ejemplo, `Hashtable<K, V>` estaría representado por `ICorDebugClass`, mientras que `Hashtable<Int32, String>` estaría representado por `ICorDebugType`.  
  
 Los tipos no genéricos se representan mediante dos `ICorDebugClass` y `ICorDebugType`. La última interfaz se introdujo en la versión 2.0 de .NET Framework para tratar con la creación de instancias de tipo.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
