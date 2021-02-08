---
description: 'Más información sobre: ICorDebugVirtualUnwinder:: GetContext (método)'
title: ICorDebugVirtualUnwinder::GetContext (método)
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
ms.openlocfilehash: 864f32ce82149658b2d4a617b08e8d7aa41fe642
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790534"
---
# <a name="icordebugvirtualunwindergetcontext-method"></a>ICorDebugVirtualUnwinder::GetContext (método)

Obtiene el contexto actual de este responsable del desenredado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `contextFlags`  
 [in] Marcas que indican qué partes del contexto se devuelven (definidas en WinNT.h).  
  
 `cbContextBuf`  
 [in] Número de bytes en `contextBuf`.  
  
 `contextSize`  
 [out] Puntero al número de bytes escritos realmente en `contextBuf`.  
  
 `contextBuf`  
 [out] Matriz de bytes que contiene el contexto actual de este responsable del desenredado.  
  
## <a name="return-value"></a>Valor devuelto  

 Cualquier valor HRESULT de error recibido por mscordbi es irrecuperable y hará que las API ICorDebug devuelvan `CORDBG_E_DATA_TARGET_ERROR`.  
  
## <a name="remarks"></a>Observaciones  

 Establezca el valor inicial del `contextBuf` argumento en el búfer de contexto devuelto mediante una llamada al método [ICorDebugStackWalk:: getContext](icordebugstackwalk-getcontext-method.md) .  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
 Dado que es posible que el desenredado solo restaure un subconjunto de los registros, por ejemplo, solo los registros no volátiles, puede que el contexto no coincida exactamente con el estado del registro en el momento de la llamada al método real.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
