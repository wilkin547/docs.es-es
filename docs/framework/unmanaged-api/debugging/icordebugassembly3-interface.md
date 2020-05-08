---
title: Interfaz ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: 67707092c80b0e07aa284336c426aba09ff991af
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894824"
---
# <a name="icordebugassembly3-interface"></a>Interfaz ICorDebugAssembly3
Extiende la interfaz ICorDebugAssembly de manera lógica para proporcionar compatibilidad con los ensamblados de contenedor y con los ensamblados que estos contienen.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnumerateContainedAssemblies](icordebugassembly3-enumeratecontainedassemblies-method.md)|Obtiene un enumerador para los ensamblados contenidos en este ensamblado.|  
|[Método GetContainerAssembly](icordebugassembly3-getcontainerassembly-method.md)|Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> La interfaz solo está disponible con .NET Native. Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
