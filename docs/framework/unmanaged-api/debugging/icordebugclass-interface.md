---
title: ICorDebugClass (Interfaz)
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
ms.openlocfilehash: 5714597b5e5ca2936aad53217ae934684e75585c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125749"
---
# <a name="icordebugclass-interface"></a>ICorDebugClass (Interfaz)

Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetModule (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Obtiene el módulo que define esta clase.|  
|[GetStaticFieldValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|Obtiene el valor del campo estático especificado.|  
|[GetToken (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|Obtiene el token de metadatos de `TypeDef` para esta clase.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz `ICorDebugClass` representa un tipo genérico sin instancias. La interfaz ICorDebugType representa un tipo genérico con instancias. Por ejemplo, `Hashtable<K, V>` se representará mediante `ICorDebugClass`, mientras que `Hashtable<Int32, String>` se representará mediante `ICorDebugType`.  
  
 Los tipos no genéricos están representados por `ICorDebugClass` y `ICorDebugType`. La última interfaz se presentó en la .NET Framework versión 2,0 para tratar con la creación de instancias de tipo.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
