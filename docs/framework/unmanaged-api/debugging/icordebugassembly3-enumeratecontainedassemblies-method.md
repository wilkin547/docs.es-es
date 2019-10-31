---
title: Método ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
ms.openlocfilehash: 032f32a08efa92cea682b0e2fc974dc607a9dca4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133937"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a>Método ICorDebugAssembly3::EnumerateContainedAssemblies
Obtiene un enumerador para los ensamblados contenidos en este ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppAssemblies`  
 enuncia Puntero a la dirección de un objeto de interfaz ICorDebugAssemblyEnum que es el enumerador.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si el objeto `ICorDebugAssembly3` es un contenedor; de lo contrario, `S_FALSE` y la enumeración está vacía.  
  
## <a name="remarks"></a>Comentarios  
 Se necesitan símbolos para enumerar los ensamblados contenidos. Si no existen, el método devuelve `S_FALSE` y no se proporciona un enumerador válido.  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugAssembly3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
