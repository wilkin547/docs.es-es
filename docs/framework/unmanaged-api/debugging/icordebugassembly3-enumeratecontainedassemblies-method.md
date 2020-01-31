---
title: Método ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
ms.openlocfilehash: 616675f839e562227558ece440bdfdf497747572
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784561"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a>Método ICorDebugAssembly3::EnumerateContainedAssemblies
Obtiene un enumerador para los ensamblados contenidos en este ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppAssemblies`  
 [out] Puntero a la dirección de un objeto de interfaz ICorDebugAssemblyEnum que es el enumerador.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si el objeto `ICorDebugAssembly3` es un contenedor; de lo contrario, `S_FALSE` y la enumeración está vacía.  
  
## <a name="remarks"></a>Notas  
 Se necesitan símbolos para enumerar los ensamblados contenidos. Si no existen, el método devuelve `S_FALSE` y no se proporciona un enumerador válido.  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugAssembly3 (interfaz)](icordebugassembly3-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
