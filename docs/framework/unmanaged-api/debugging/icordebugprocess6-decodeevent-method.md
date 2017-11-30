---
title: "Método ICorDebugProcess6::DecodeEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c0186fb91a4c47f1988af58577cee1b7a64987a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6decodeevent-method"></a>Método ICorDebugProcess6::DecodeEvent
Descodifica los eventos de depuración administrados encapsulados en la carga de los eventos de depuración de excepción nativos especialmente diseñados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pRecord`  
 [in] Puntero a una matriz de bytes desde un evento de depuración de excepción nativo que incluye información acerca de un evento de depuración administrado.  
  
 `countBytes`  
 [in] Número de elementos en la matriz de bytes `pRecord`.  
  
 `format`  
 [in] A [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) miembro de enumeración que especifica el formato del evento de depuración no administrada.  
  
 `dwFlags`  
 [in] Campo de bits que depende de la arquitectura de destino y que especifica más información sobre el evento de depuración. Para los sistemas de Windows, puede ser un miembro de la [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) enumeración.  
  
 `dwThreadId`  
 [in] Identificador del sistema operativo del subproceso en el que se produjo la excepción.  
  
 `ppEvent`  
 [out] Un puntero a la dirección de un [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) objeto que representa un evento de depuración administrado descodificado.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaz ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
