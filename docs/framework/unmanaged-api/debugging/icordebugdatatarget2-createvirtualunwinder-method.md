---
title: "Método ICorDebugDataTarget2::CreateVirtualUnwinder"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 421cff28e84106c0859889e6f9e99e870b469a98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a>Método ICorDebugDataTarget2::CreateVirtualUnwinder
Crea un nuevo desenredador de pila que inicia el desenredo desde un contexto inicial (que no tiene por qué ser la hoja de un subproceso).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
#### <a name="parameters"></a>Parámetros  
 nativeThreadID  
 [in] Identificador de subproceso nativo del subproceso cuya pila se va a desenredar.  
  
 contextFlags  
 [in] Marcas que indican qué partes del contexto se definen en `initialContext`.  
  
 cbContext  
 [in] Tamaño de `initialContext`.  
  
 initialContext  
 [in] Los datos en el contexto.  
  
 ppUnwinder  
 [out] Puntero a la dirección de un objeto de la interfaz ICorDebugVirtualUnwinder.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si se realiza correctamente. Cualquier otro `HRESULT` indica un error. Cualquier error `HRESULT` recibido por mscordbi es irrecuperable y hace que [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) métodos para devolver `CORDBG_E_DATA_TARGET_ERROR`.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaz ICorDebugDataTarget2](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
