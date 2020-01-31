---
title: Método ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 969cca6d5613670fc4b26fc973785b4874c3684c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778068"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a>Método ICorDebugAssembly3::GetContainerAssembly
Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppAssembly`  
 Puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado de contenedor, o **null** si se produce un error en la llamada al método.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si la llamada al método se realiza correctamente; de lo contrario, `S_FALSE`y `ppAssembly` es **null**.  
  
## <a name="remarks"></a>Notas  
 Si este ensamblado se ha combinado con otros dentro de un solo ensamblado de contenedor, este método devuelve el ensamblado de contenedor. Para obtener más información y terminología, vea el tema [método icordebugprocess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .  
  
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
