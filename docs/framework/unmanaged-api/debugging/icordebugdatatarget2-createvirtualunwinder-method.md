---
description: 'Más información sobre: método icordebugdatatarget2:: CreateVirtualUnwinder (método)'
title: Método ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: 0646c85000f42b303769d6587354b3105e2deabd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764416"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a>Método ICorDebugDataTarget2::CreateVirtualUnwinder

Crea un nuevo desenredador de pila que inicia el desenredo desde un contexto inicial (que no tiene por qué ser la hoja de un subproceso).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a>Parámetros  

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

 `S_OK` si se realiza correctamente. Cualquier otro `HRESULT` indica un error. Cualquier error `HRESULT` recibido por mscordbi se considera fatal y hace que los métodos [ICorDebug](icordebug-interface.md) devuelvan `CORDBG_E_DATA_TARGET_ERROR` .  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
