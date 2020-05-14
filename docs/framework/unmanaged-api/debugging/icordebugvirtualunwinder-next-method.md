---
title: ICorDebugVirtualUnwinder::Next (método)
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
ms.openlocfilehash: 55f10a6148f0b11cf74492afe947d5921a1d1458
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396424"
---
# <a name="icordebugvirtualunwindernext-method"></a>ICorDebugVirtualUnwinder::Next (método)
Avanza hasta el contexto del llamador.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a>Parámetros  
 Ninguno.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` Si el desenredado se realizó correctamente o `CORDBG_S_AT_END_OF_STACK` si el desenredado no se puede completar porque no hay más marcos.  
  
 Si se devuelve un error HRESULT, las API ICorDebug devolverán `CORDBG_E_DATA_TARGET_ERROR`.  
  
## <a name="remarks"></a>Comentarios  
 El rastreador de pila debe garantizar que permite avanzar, de manera que una posible llamada a `Next` devuelva un error HRESULT o `CORDBG_S_AT_END_OF_STACK`. Devolver `S_OK` indefinidamente puede producir un bucle infinito.  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
