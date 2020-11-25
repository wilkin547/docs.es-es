---
title: Interfaz ICorDebugProcess6
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
ms.openlocfilehash: ba70bab28eeddad6e3cf3c2b82b196a69ce68647
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732611"
---
# <a name="icordebugprocess6-interface"></a>Interfaz ICorDebugProcess6

Extiende la interfaz ICorDebugProcess de manera lógica para habilitar características como la descodificación de eventos de depuración administrados que están codificados en eventos de depuración de excepción nativos o la división de módulos virtuales.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método DecodeEvent](icordebugprocess6-decodeevent-method.md)|Descodifica los eventos de depuración administrados encapsulados en la carga de los eventos de depuración de excepción nativos especialmente diseñados.|  
|[Método EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md)|Habilita o deshabilita la división de módulos virtuales.|  
|[Método GetCode](icordebugprocess6-getcode-method.md)|Obtiene información sobre el código administrado en una dirección de código determinado.|  
|[Método GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md)|Proporciona información sobre las funciones exportadas en tiempo de ejecución para ayudar a recorrer el código administrado.|  
|[Método MarkDebuggerAttached](icordebugprocess6-markdebuggerattached-method.md)|Cambia el estado interno del código que se está depurando para que el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> de la biblioteca de clases .NET Framework devuelva `true`.|  
|[Método ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)|Notifica a [ICorDebug](icordebug-interface.md) que el proceso se está ejecutando.|  
  
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
