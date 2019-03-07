---
title: ICorDebugVirtualUnwinder::GetContext (método)
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a554efc89c1242537bec7de074220cbec95ecdd2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481139"
---
# <a name="icordebugvirtualunwindergetcontext-method"></a>ICorDebugVirtualUnwinder::GetContext (método)
Obtiene el contexto actual de este responsable del desenredado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
## <a name="remarks"></a>Comentarios  
 Establezca el valor inicial de la `contextBuf` argumento para el búfer de contexto devuelto por una llamada a la [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) método.  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
 Dado que es posible que el desenredado solo restaure un subconjunto de los registros, por ejemplo, solo los registros no volátiles, puede que el contexto no coincida exactamente con el estado del registro en el momento de la llamada al método real.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorDebugMemoryBuffer (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
