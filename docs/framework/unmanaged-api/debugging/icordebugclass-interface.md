---
description: 'Más información acerca de: ICorDebugClass (interfaz)'
title: Interfaz ICorDebugClass
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
ms.openlocfilehash: 5ded26a8b3a98bd273bbfe1bfa9efd1bb70d5595
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711510"
---
# <a name="icordebugclass-interface"></a>Interfaz ICorDebugClass

Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetModule (Método)](icordebugclass-getmodule-method.md)|Obtiene el módulo que define esta clase.|  
|[Método GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md)|Obtiene el valor del campo estático especificado.|  
|[GetToken (Método)](icordebugclass-gettoken-method.md)|Obtiene el `TypeDef` símbolo (token) de metadatos de esta clase.|  
  
## <a name="remarks"></a>Observaciones  

 La `ICorDebugClass` interfaz representa un tipo genérico sin instancias. La interfaz ICorDebugType representa un tipo genérico con instancias. Por ejemplo, `Hashtable<K, V>` se representará mediante `ICorDebugClass` , mientras que `Hashtable<Int32, String>` se representaría mediante `ICorDebugType` .  
  
 Los tipos no genéricos están representados por `ICorDebugClass` y `ICorDebugType` . La última interfaz se presentó en la .NET Framework versión 2,0 para tratar con la creación de instancias de tipo.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
