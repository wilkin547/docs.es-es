---
title: Interfaz ICorDebugProcess6
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
ms.openlocfilehash: ac26402903ecf437fa9654e91cef8b44ff033358
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123449"
---
# <a name="icordebugprocess6-interface"></a>Interfaz ICorDebugProcess6
Extiende lógicamente la interfaz ICorDebugProcess para habilitar características como la descodificación de eventos de depuración administrados codificados en eventos de depuración de excepción nativa y la división de módulos virtuales.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[DecodeEvent (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)|Descodifica los eventos de depuración administrados encapsulados en la carga de los eventos de depuración de excepción nativos especialmente diseñados.|  
|[EnableVirtualModuleSplitting (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)|Habilita o deshabilita la división de módulos virtuales.|  
|[GetCode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getcode-method.md)|Obtiene información sobre el código administrado en una dirección de código determinado.|  
|[GetExportStepInfo (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)|Proporciona información sobre las funciones exportadas en tiempo de ejecución para ayudar a recorrer el código administrado.|  
|[MarkDebuggerAttached (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-markdebuggerattached-method.md)|Cambia el estado interno del código que se está depurando para que el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> de la biblioteca de clases .NET Framework devuelva `true`.|  
|[ProcessStateChanged (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)|Notifica a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que el proceso se está ejecutando.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> La interfaz solo está disponible con .NET Native. Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
