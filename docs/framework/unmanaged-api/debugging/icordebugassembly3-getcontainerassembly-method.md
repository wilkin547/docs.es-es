---
description: 'Más información sobre: método icordebugassembly3:: GetContainerAssembly (método)'
title: Método ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 5a6bc6dfb1c8403137a9444ff1cc4f64e75da65d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791522"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a>Método ICorDebugAssembly3::GetContainerAssembly

Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppAssembly`  
 Puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado de contenedor, o **null** si se produce un error en la llamada al método.  
  
## <a name="return-value"></a>Valor devuelto  

 `S_OK` Si la llamada al método se realiza correctamente; de lo contrario, `S_FALSE` y `ppAssembly` es **null**.  
  
## <a name="remarks"></a>Observaciones  

 Si este ensamblado se ha combinado con otros dentro de un solo ensamblado de contenedor, este método devuelve el ensamblado de contenedor. Para obtener más información y terminología, vea el tema [método icordebugprocess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugAssembly3](icordebugassembly3-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
