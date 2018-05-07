---
title: ICorDebugVirtualUnwinder::Next (método)
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4bacbd9ef11f6f6cb6d9952290c00f1b8ce50aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugvirtualunwindernext-method"></a>ICorDebugVirtualUnwinder::Next (método)
Avanza hasta el contexto del llamador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Next();  
```  
  
#### <a name="parameters"></a>Parámetros  
 Ninguno.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` Si el desenredado se realizó correctamente o `CORDBG_S_AT_END_OF_STACK` si el desenredado no se puede completar porque no hay más marcos.  
  
 Si se devuelve un error HRESULT, las API ICorDebug devolverán `CORDBG_E_DATA_TARGET_ERROR`.  
  
## <a name="remarks"></a>Comentarios  
 El rastreador de pila debe garantizar que permite avanzar, de manera que una posible llamada a `Next` devuelva un error HRESULT o `CORDBG_S_AT_END_OF_STACK`. Devolver `S_OK` indefinidamente puede provocar un bucle infinito.  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugMemoryBuffer (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
