---
title: Interfaz ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: 0260267a05a880fbb3ac48325e55deff326f5f87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688372"
---
# <a name="icordebugassembly3-interface"></a>Interfaz ICorDebugAssembly3

Extiende la interfaz ICorDebugAssembly de manera lógica para proporcionar compatibilidad con los ensamblados de contenedor y con los ensamblados que estos contienen.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnumerateContainedAssemblies](icordebugassembly3-enumeratecontainedassemblies-method.md)|Obtiene un enumerador para los ensamblados contenidos en este ensamblado.|  
|[Método GetContainerAssembly](icordebugassembly3-getcontainerassembly-method.md)|Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> La interfaz solo está disponible con .NET Native. Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
