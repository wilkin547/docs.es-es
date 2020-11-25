---
title: Interfaz ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: aa1db39b564b987fb8d0f79d529f5af59b7e4c02
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713761"
---
# <a name="icordebugdatatarget2-interface"></a>Interfaz ICorDebugDataTarget2

Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CreateVirtualUnwinder](icordebugdatatarget2-createvirtualunwinder-method.md)|Crea un nuevo desenredador de pila que inicia el desenredo desde un contexto inicial (que no tiene por qué ser la hoja de un subproceso).|  
|[Método EnumerateThreadIDs](icordebugdatatarget2-enumeratethreadids-method.md)|Devuelve una lista de identificadores de subprocesos activos.|  
|[Método GetImageFromPointer](icordebugdatatarget2-getimagefrompointer-method.md)|Devuelve el tamaño y dirección base del módulo a partir de una dirección de ese módulo.|  
|[Método GetImageLocation](icordebugdatatarget2-getimagelocation-method.md)|Devuelve la ruta de acceso de un módulo a partir de la dirección base del módulo.|  
|[Método GetSymbolProviderForImage](icordebugdatatarget2-getsymbolproviderforimage-method.md)|Devuelve el proveedor de símbolos de un módulo a partir de la dirección base de ese módulo.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz solo está disponible con .NET Native. Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
