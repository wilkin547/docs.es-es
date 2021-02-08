---
description: 'Más información acerca de: ICorDebugObjectValue (interfaz)'
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
ms.openlocfilehash: a2af438bbb4c2f56eb1a72151e339b6b0a978eec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794780"
---
# <a name="icordebugobjectvalue-interface"></a>Interfaz ICorDebugObjectValue

Subclase de "ICorDebugValue" que representa un valor que contiene un objeto.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetClass](icordebugobjectvalue-getclass-method.md)|Obtiene un puntero de interfaz al Common Language Runtime (CLR) <xref:System.Type> del objeto al que `ICorDebugObjectValue` hace referencia.|  
|[Método GetContext](icordebugobjectvalue-getcontext-method.md)|Sin implementar.|  
|[Método GetFieldValue](icordebugobjectvalue-getfieldvalue-method.md)|Obtiene un puntero de interfaz a un [ICorDebugValue](icordebugvalue-interface.md) que representa el valor del campo especificado de la clase especificada.|  
|[Método GetManagedCopy](icordebugobjectvalue-getmanagedcopy-method.md)|Obsoleto. No llame a este método.|  
|[Método GetVirtualMethod](icordebugobjectvalue-getvirtualmethod-method.md)|Sin implementar.|  
|[Método IsValueClass](icordebugobjectvalue-isvalueclass-method.md)|Obtiene un valor que indica si el objeto al que hace referencia este objeto `ICorDebugObjectValue` es un tipo de valor.|  
|[Método SetFromManagedCopy](icordebugobjectvalue-setfrommanagedcopy-method.md)|Obsoleto. No llame a este método.|  
  
## <a name="remarks"></a>Observaciones  

 Un `ICorDebugObjectValue` sigue siendo válido hasta que continúe el proceso que se está depurando.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
