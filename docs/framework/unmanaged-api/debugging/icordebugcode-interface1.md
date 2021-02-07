---
description: 'Más información acerca de: ICorDebugCode (interfaz)'
title: Interfaz ICorDebugCode
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
ms.openlocfilehash: ce67c48501783bbe00152f0ba2c224e6e7dde6d7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711159"
---
# <a name="icordebugcode-interface"></a>Interfaz ICorDebugCode

Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CreateBreakpoint](icordebugcode-createbreakpoint-method.md)|Crea un punto de interrupción en el desplazamiento especificado.|  
|[Método GetAddress](icordebugcode-getaddress-method.md)|Obtiene la dirección virtual relativa (RVA) del segmento de código que representa `ICorDebugCode`.|  
|[Método GetCode](icordebugcode-getcode-method.md)|Obtiene todo el código para la función especificada, con formato de desensamblado. Este método está en desuso; Use [ICorDebugCode2:: getcodechunks (](icordebugcode2-getcodechunks-method.md) en su lugar.|  
|[Método GetEnCRemapSequencePoints](icordebugcode-getencremapsequencepoints-method.md)|Sin implementar.|  
|[Método GetFunction](icordebugcode-getfunction-method.md)|Obtiene la "ICorDebugFunction" asociada a este `ICorDebugCode` .|  
|[Método GetILToNativeMapping](icordebugcode-getiltonativemapping-method.md)|Obtiene una matriz de instancias "COR_DEBUG_IL_TO_NATIVE_MAP" que representan asignaciones de desplazamientos MSIL a desplazamientos nativos.|  
|[Método GetSize](icordebugcode-getsize-method.md)|Obtiene el tamaño, en bytes, del código binario representado por esta instancia de `ICorDebugCode`.|  
|[GetVersionNumber (Método)](icordebugcode-getversionnumber-method.md)|Obtiene el número basado en uno que identifica la versión del código que representa esta instancia de `ICorDebugCode`.|  
|[Método IsIL](icordebugcode-isil-method.md)|Obtiene un valor que indica si esta instancia de `ICorDebugCode` está compilada en MSIL.|  
  
## <a name="remarks"></a>Observaciones  

 `ICorDebugCode` puede representar MSIL o código nativo. Un objeto "ICorDebugFunction" que representa el código MSIL puede tener o ninguno de los `ICorDebugCode` objetos asociados. Un objeto "ICorDebugFunction" que representa el código nativo puede tener cualquier número de `ICorDebugCode` objetos asociados a él.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugCode3 (Interfaz)](icordebugcode3-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
