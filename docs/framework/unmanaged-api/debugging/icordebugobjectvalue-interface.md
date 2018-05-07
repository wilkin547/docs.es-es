---
title: ICorDebugObjectValue Interfaz1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ddf3b60ed595aff8bc81d0bb59675fd1db12f7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugobjectvalue-interface1"></a>ICorDebugObjectValue Interfaz1
Una subclase de "ICorDebugValue" que representa un valor que contiene un objeto.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|Obtiene un puntero de interfaz a common language runtime (CLR) <xref:System.Type> del objeto que este `ICorDebugObjectValue` referencias.|  
|[GetContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|Sin implementar.|  
|[GetFieldValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|Obtiene un puntero de interfaz a una [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) que representa el valor del campo especificado de la clase especificada.|  
|[GetManagedCopy (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|Obsoleto. No llame a este método.|  
|[GetVirtualMethod (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|Sin implementar.|  
|[IsValueClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|Obtiene un valor que indica si el objeto al que hace referencia este `ICorDebugObjectValue` es un tipo de valor.|  
|[SetFromManagedCopy (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|Obsoleto. No llame a este método.|  
  
## <a name="remarks"></a>Comentarios  
 Un `ICorDebugObjectValue` sigue siendo válida hasta que se continúa el proceso que se está depurando.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 
