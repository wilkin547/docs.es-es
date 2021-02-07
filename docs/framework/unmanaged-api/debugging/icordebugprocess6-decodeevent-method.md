---
description: 'Más información acerca de: método icordebugprocess6::D ecodeEvent (método)'
title: Método ICorDebugProcess6::DecodeEvent
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: 241b24335f96a250156effde34683c8f32a47e3f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746222"
---
# <a name="icordebugprocess6decodeevent-method"></a>Método ICorDebugProcess6::DecodeEvent

Descodifica los eventos de depuración administrados encapsulados en la carga de los eventos de depuración de excepción nativos especialmente diseñados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,
        [in] DWORD dwThreadId,
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pRecord`  
 [in] Puntero a una matriz de bytes desde un evento de depuración de excepción nativo que incluye información acerca de un evento de depuración administrado.  
  
 `countBytes`  
 [in] Número de elementos en la matriz de bytes `pRecord`.  
  
 `format`  
 de Miembro de la enumeración [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) que especifica el formato del evento de depuración no administrada.  
  
 `dwFlags`  
 [in] Campo de bits que depende de la arquitectura de destino y que especifica más información sobre el evento de depuración. En el caso de los sistemas Windows, puede ser un miembro de la enumeración [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) .  
  
 `dwThreadId`  
 [in] Identificador del sistema operativo del subproceso en el que se produjo la excepción.  
  
 `ppEvent`  
 enuncia Puntero a la dirección de un objeto [ICorDebugDebugEvent](icordebugdebugevent-interface.md) que representa un evento de depuración administrada descodificada.  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugProcess6](icordebugprocess6-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
