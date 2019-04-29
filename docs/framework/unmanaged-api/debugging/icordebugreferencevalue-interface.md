---
title: Interfaz ICorDebugReferenceValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6575acfb1f75cbc8e3d59ddca5fea0953274cf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782959"
---
# <a name="icordebugreferencevalue-interface"></a>Interfaz ICorDebugReferenceValue
Proporciona métodos que administran un valor que es una referencia a un objeto. (Es decir, esta interfaz proporciona métodos que administran un puntero). Esta interfaz implementa "ICorDebugValue".  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Dereference (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|Obtiene el objeto que se hace referencia.|  
|[DereferenceStrong (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|Sin implementar. No llame a este método.|  
|[GetValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|Obtiene la dirección de memoria actual del objeto que se hace referencia.|  
|[IsNull (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|Obtiene un valor que indica si este `ICorDebugReferenceValue` es un valor null, en cuyo caso el `ICorDebugReferenceValue` no apunta a un objeto.|  
|[SetValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|Establece la dirección de memoria actual. Es decir, este método establece esto `ICorDebugReferenceValue` para que apunte a un objeto.|  
  
## <a name="remarks"></a>Comentarios  
 Common language runtime (CLR) puede hacer una recolección en objetos cuando se continúa el proceso depurado. La colección de elementos no utilizados puede mover los objetos en memoria. Un `ICorDebugReferenceValue` cualquiera cooperarán con la recolección de elementos para que su información se actualiza después de la recolección de elementos no utilizados o quedarán invalidado implícitamente antes de la colección de elementos no utilizados.  
  
 La `ICorDebugReferenceValue` objeto puede invalidar implícitamente después de que se ha reanudado el proceso depurado. No se invalida la derivada "ICorDebugHandleValue" hasta que se publicó o se exponen explícitamente.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
