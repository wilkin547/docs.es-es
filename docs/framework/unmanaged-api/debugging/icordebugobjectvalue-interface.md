---
title: Interfaz ICorDebugObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: e104f8c522af2ee4cd42332b7459f4a2fd185511
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792686"
---
# <a name="icordebugobjectvalue-interface"></a>Interfaz ICorDebugObjectValue

Subclase de "ICorDebugValue" que representa un valor que contiene un objeto.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetClass (método)](icordebugobjectvalue-getclass-method.md)|Obtiene un puntero de interfaz a la <xref:System.Type> de Common Language Runtime (CLR) del objeto al que hace referencia este `ICorDebugObjectValue`.|  
|[GetContext (método)](icordebugobjectvalue-getcontext-method.md)|Sin implementar.|  
|[GetFieldValue (método)](icordebugobjectvalue-getfieldvalue-method.md)|Obtiene un puntero de interfaz a un [ICorDebugValue](icordebugvalue-interface.md) que representa el valor del campo especificado de la clase especificada.|  
|[GetManagedCopy (método)](icordebugobjectvalue-getmanagedcopy-method.md)|Obsoleta. No llame a este método.|  
|[GetVirtualMethod (método)](icordebugobjectvalue-getvirtualmethod-method.md)|Sin implementar.|  
|[IsValueClass (método)](icordebugobjectvalue-isvalueclass-method.md)|Obtiene un valor que indica si el objeto al que hace referencia este `ICorDebugObjectValue` es un tipo de valor.|  
|[SetFromManagedCopy (método)](icordebugobjectvalue-setfrommanagedcopy-method.md)|Obsoleta. No llame a este método.|  
  
## <a name="remarks"></a>Notas  
 Un `ICorDebugObjectValue` sigue siendo válido hasta que se continúa el proceso que se está depurando.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
