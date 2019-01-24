---
title: CorDebugInterfaceVersion (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugInterfaceVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInterfaceVersion
helpviewer_keywords:
- CorDebugInterfaceVersion enumeration [.NET Framework debugging]
ms.assetid: 7d1e6cd9-2a15-41c6-9b68-008705a4ed90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bc72b9c5687654c17a01ee9b4fa9d31dcf50b56
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556121"
---
# <a name="cordebuginterfaceversion-enumeration"></a>CorDebugInterfaceVersion (Enumeración)
Especifica una interfaz, una versión de .NET Framework, o la versión de .NET Framework en la que se incorporó una interfaz.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorDebugInterfaceVersion {  
  
    CorDebugInvalidVersion            = 0,  
    CorDebugVersion_1_0               = CorDebugInvalidVersion + 1,  
  
    ver_ICorDebugManagedCallback      = CorDebugVersion_1_0,  
    ver_ICorDebugUnmanagedCallback    = CorDebugVersion_1_0,  
    ver_ICorDebug                     = CorDebugVersion_1_0,  
    ver_ICorDebugController           = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomain            = CorDebugVersion_1_0,  
    ver_ICorDebugAssembly             = CorDebugVersion_1_0,  
    ver_ICorDebugProcess              = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpoint           = CorDebugVersion_1_0,  
    ver_ICorDebugFunctionBreakpoint   = CorDebugVersion_1_0,  
    ver_ICorDebugModuleBreakpoint     = CorDebugVersion_1_0,  
    ver_ICorDebugValueBreakpoint      = CorDebugVersion_1_0,  
    ver_ICorDebugStepper              = CorDebugVersion_1_0,  
    ver_ICorDebugRegisterSet          = CorDebugVersion_1_0,  
    ver_ICorDebugThread               = CorDebugVersion_1_0,  
    ver_ICorDebugChain                = CorDebugVersion_1_0,  
    ver_ICorDebugFrame                = CorDebugVersion_1_0,  
    ver_ICorDebugILFrame              = CorDebugVersion_1_0,  
    ver_ICorDebugNativeFrame          = CorDebugVersion_1_0,  
    ver_ICorDebugModule               = CorDebugVersion_1_0,  
    ver_ICorDebugFunction             = CorDebugVersion_1_0,  
    ver_ICorDebugCode                 = CorDebugVersion_1_0,  
    ver_ICorDebugClass                = CorDebugVersion_1_0,  
    ver_ICorDebugEval                 = CorDebugVersion_1_0,  
    ver_ICorDebugValue                = CorDebugVersion_1_0,  
    ver_ICorDebugGenericValue         = CorDebugVersion_1_0,  
    ver_ICorDebugReferenceValue       = CorDebugVersion_1_0,  
    ver_ICorDebugHeapValue            = CorDebugVersion_1_0,  
    ver_ICorDebugObjectValue          = CorDebugVersion_1_0,  
    ver_ICorDebugBoxValue             = CorDebugVersion_1_0,  
    ver_ICorDebugStringValue          = CorDebugVersion_1_0,  
    ver_ICorDebugArrayValue           = CorDebugVersion_1_0,  
    ver_ICorDebugContext              = CorDebugVersion_1_0,  
    ver_ICorDebugEnum                 = CorDebugVersion_1_0,  
    ver_ICorDebugObjectEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpointEnum       = CorDebugVersion_1_0,  
    ver_ICorDebugStepperEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugProcessEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugThreadEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugFrameEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugChainEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugModuleEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugValueEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugCodeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugTypeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugErrorInfoEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomainEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAssemblyEnum         = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueErrorInfo   
                                      = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueSnapshot   
                                      = CorDebugVersion_1_0,  
  
    CorDebugVersion_1_1               = CorDebugVersion_1_0 + 1,  
    // No interface definitions in version 1.1.  
  
    CorDebugVersion_2_0 = CorDebugVersion_1_1 + 1,  
  
    ver_ICorDebugManagedCallback2    = CorDebugVersion_2_0,  
    ver_ICorDebugAppDomain2          = CorDebugVersion_2_0,  
    ver_ICorDebugProcess2            = CorDebugVersion_2_0,  
    ver_ICorDebugStepper2            = CorDebugVersion_2_0,  
    ver_ICorDebugRegisterSet2        = CorDebugVersion_2_0,  
    ver_ICorDebugThread2             = CorDebugVersion_2_0,  
    ver_ICorDebugILFrame2            = CorDebugVersion_2_0,  
    ver_ICorDebugModule2             = CorDebugVersion_2_0,  
    ver_ICorDebugFunction2           = CorDebugVersion_2_0,  
    ver_ICorDebugCode2               = CorDebugVersion_2_0,  
    ver_ICorDebugClass2              = CorDebugVersion_2_0,  
    ver_ICorDebugValue2              = CorDebugVersion_2_0,  
    ver_ICorDebugEval2               = CorDebugVersion_2_0,  
    ver_ICorDebugObjectValue2        = CorDebugVersion_2_0,  
  
    // CLR v4 - next major CLR version after CLR v2  
    // Includes Silverlight 4  
    CorDebugVersion_4_0 = CorDebugVersion_2_0 + 1,  
  
    ver_ICorDebugThread3             = CorDebugVersion_4_0,  
    ver_ICorDebugThread4             = CorDebugVersion_4_0,  
    ver_ICorDebugStackWalk           = CorDebugVersion_4_0,  
    ver_ICorDebugNativeFrame2        = CorDebugVersion_4_0,  
    ver_ICorDebugInternalFrame2      = CorDebugVersion_4_0,  
    ver_ICorDebugRuntimeUnwindableFrame = CorDebugVersion_4_0,  
    ver_ICorDebugHeapValue3          = CorDebugVersion_4_0,  
    ver_ICorDebugBlockingObjectEnum  = CorDebugVersion_4_0,  
    ver_ICorDebugValue3 = CorDebugVersion_4_0,  
  
    CorDebugVersion_4_5 = CorDebugVersion_4_0 + 1,  
  
    ver_ICorDebugComObjectValue = CorDebugVersion_4_5,  
    ver_ICorDebugAppDomain3 = CorDebugVersion_4_5,  
    ver_ICorDebugCode3 = CorDebugVersion_4_5,  
    ver_ICorDebugILFrame3 = CorDebugVersion_4_5,  
  
    CorDebugLatestVersion = CorDebugVersion_4_5  
  
} CorDebugInterfaceVersion;  
```  
  
## <a name="members"></a>Miembros  
 En la tabla siguiente se incluyen vínculos de cada valor de enumeración a la interfaz correspondiente. Además, la tabla indica la primera versión de .NET Framework en la que se admitía la interfaz.  
  
|Miembro|Especifica|Versión de .NET Framework|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|La versión de .NET Framework no es válida.|-|  
|`CorDebugVersion_1_0`|La versión de .NET Framework, incluidos todos sus Service Packs, es 1.0.|1.0|  
|`CorDebugVersion_1_1`|La versión de .NET Framework, incluidos todos los Service Packs, es 1.1.|1.1|  
|`CorDebugVersion_2_0`|La versión de .NET Framework, incluidos todos los Service Packs, es 2,0.|2.0|  
|`CorDebugVersion_4_0`|La versión de .NET Framework, incluidos todos los Service Packs, es 4.|4|  
|`CorDebugVersion_4_5`|La versión de .NET Framework, incluidos todos los Service Packs, es 4,5.|4.5|  
|`ver_ICorDebugManagedCallback`|[ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)|1.0|  
|`ver_ICorDebugUnmanagedCallback`|[ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)|1.0|  
|`ver_ICorDebug`|[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)|1.0|  
|`ver_ICorDebugController`|[ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)|1.0|  
|`ver_ICorDebugAppDomain`|[ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)|1.0|  
|`ver_ICorDebugAssembly`|[ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)|1.0|  
|`ver_ICorDebugProcess`|[ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)|1.0|  
|`ver_ICorDebugBreakpoint`|[ICorDebugBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)|1.0|  
|`ver_ICorDebugFunctionBreakpoint`|[ICorDebugFunctionBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)|1.0|  
|`ver_ICorDebugModuleBreakpoint`|[ICorDebugModuleBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)|1.0|  
|`ver_ICorDebugValueBreakpoint`|[ICorDebugValueBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-interface.md)|1.0|  
|`ver_ICorDebugStepper`|[ICorDebugStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)|1.0|  
|`ver_ICorDebugRegisterSet`|[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)|1.0|  
|`ver_ICorDebugThread`|[ICorDebugThread](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)|1.0|  
|`ver_ICorDebugChain`|[ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)|1.0|  
|`ver_ICorDebugFrame`|[ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)|1.0|  
|`ver_ICorDebugILFrame`|[ICorDebugILFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)|1.0|  
|`ver_ICorDebugNativeFrame`|[ICorDebugNativeFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)|1.0|  
|`ver_ICorDebugModule`|[ICorDebugModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)|1.0|  
|`ver_ICorDebugFunction`|[ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)|1.0|  
|`ver_ICorDebugCode`|[ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)|1.0|  
|`ver_ICorDebugClass`|[ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)|1.0|  
|`ver_ICorDebugEval`|[ICorDebugEval](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)|1.0|  
|`ver_ICorDebugValue`|[ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md)|1.0|  
|`ver_ICorDebugGenericValue`|[ICorDebugGenericValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)|1.0|  
|`ver_ICorDebugReferenceValue`|[ICorDebugReferenceValue](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)|1.0|  
|`ver_ICorDebugHeapValue`|[ICorDebugHeapValue](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)|1.0|  
|`ver_ICorDebugObjectValue`|[ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)|1.0|  
|`ver_ICorDebugBoxValue`|[ICorDebugBoxValue](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)|1.0|  
|`ver_ICorDebugStringValue`|[ICorDebugStringValue](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)|1.0|  
|`ver_ICorDebugArrayValue`|[ICorDebugArrayValue](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)|1.0|  
|`ver_ICorDebugContext`|[ICorDebugContext](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)|1.0|  
|`ver_ICorDebugEnum`|[ICorDebugEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)|1.0|  
|`ver_ICorDebugObjectEnum`|[ICorDebugObjectEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)|1.0|  
|`ver_ICorDebugBreakpointEnum`|[ICorDebugBreakpointEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)|1.0|  
|`ver_ICorDebugStepperEnum`|[ICorDebugStepperEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)|1.0|  
|`ver_ICorDebugProcessEnum`|[ICorDebugProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)|1.0|  
|`ver_ICorDebugThreadEnum`|[ICorDebugThreadEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)|1.0|  
|`ver_ICorDebugFrameEnum`|[ICorDebugFrameEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)|1.0|  
|`ver_ICorDebugChainEnum`|[ICorDebugChainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)|1.0|  
|`ver_ICorDebugModuleEnum`|[ICorDebugModuleEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)|1.0|  
|`ver_ICorDebugValueEnum`|[ICorDebugValueEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvalueenum-interface.md)|1.0|  
|`ver_ICorDebugCodeEnum`|[ICorDebugCodeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)|1.0|  
|`ver_ICorDebugTypeEnum`|[ICorDebugTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)|1.0|  
|`ver_ICorDebugErrorInfoEnum`|[ICorDebugErrorInfoEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)|1.0|  
|`ver_ICorDebugAppDomainEnum`|[ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)|1.0|  
|`ver_ICorDebugAssemblyEnum`|[ICorDebugAssemblyEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)|1.0|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[ICorDebugEditAndContinueErrorInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)|1.0|  
|`ver_ICorDebugEditAndContinueSnapshot`|[ICorDebugEditAndContinueSnapshot](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)|1.0|  
|`ver_ICorDebugManagedCallback2`|[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)|2.0|  
|`ver_ICorDebugAppDomain2`|[ICorDebugAppDomain2](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)|2.0|  
|`ver_ICorDebugProcess2`|[ICorDebugProcess2](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)|2.0|  
|`ver_ICorDebugStepper2`|[ICorDebugStepper2](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)|2.0|  
|`ver_ICorDebugRegisterSet2`|[ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)|2.0|  
|`ver_ICorDebugThread2`|[ICorDebugThread2](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)|2.0|  
|`ver_ICorDebugILFrame2`|[ICorDebugILFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)|2.0|  
|`ver_ICorDebugModule2`|[ICorDebugModule2](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)|2.0|  
|`ver_ICorDebugFunction2`|[ICorDebugFunction2](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)|2.0|  
|`ver_ICorDebugCode2`|[ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)|2.0|  
|`ver_ICorDebugClass2`|"ICorDebugClass2"|2.0|  
|`ver_ICorDebugValue2`|"ICorDebugValue2"|2.0|  
|`ver_ICorDebugEval2`|"ICorDebugEval2".|2.0|  
|`ver_ICorDebugObjectValue2`|"ICorDebugObjectValue2"|2.0|  
|`ver_ICorDebugThread3`|[ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)|4|  
|`ver_ICorDebugThread4`|[ICorDebugThread4](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)|4|  
|`ver_ICorDebugStackWalk`|[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)|4|  
|`ver_ICorDebugNativeFrame2`|[ICorDebugNativeFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)|4|  
|`ver_ICorDebugInternalFrame2`|[ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)|4|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[ICorDebugRuntimeUnwindableFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)|4|  
|`ver_ICorDebugHeapValue3`|[ICorDebugHeapValue3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)|4|  
|`ver_ICorDebugBlockingObjectEnum`|[ICorDebugBlockingObjectEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)|4|  
|`ver_ICorDebugValue3`|[ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)|4|  
|`ver_ICorDebugComObjectValue`|[ICorDebugComObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)|4.5|  
|`ver_ICorDebugAppDomain3`|[ICorDebugAppDomain3](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)|4.5|  
|`ver_ICorDebugCode3`|[ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)|4.5|  
|`ver_ICorDebugILFrame3`|[ICorDebugILFrame3](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)|4.5|  
|`CorDebugLatestVersion`|La versión de .NET Framework, incluidos todos sus Service Packs, es la última versión.|-|  
  
## <a name="remarks"></a>Comentarios  
 Puede usar un depurador el `CorDebugInterfaceVersion` enumeración en el [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) función para especificar la versión más alta de .NET Framework que admite el depurador.  
  
## <a name="interface-names"></a>Nombres de interfaz  
 El número que aparece al final de los nombres de interfaz en la API de depuración (por ejemplo, "3" en `ICorDebugThread3`) especifica la versión de la interfaz, no la versión de .NET Framework. Todos los nombres de interfaz en la API de depuración incluyen números de versión, excepto las interfaces que se incorporaron en .NET Framework versión 1. Cualquier correspondencia entre los números de versión de las interfaces y los números de versión de .NET Framework es pura coincidencia.  
  
-   Las interfaces que se incorporaron en .NET Framework versión 1.0 no incluyen números, porque implícitamente son todas de la versión 1.  
  
-   .NET Framework versión 1.1 usa las interfaces de la versión 1.0 y no incorpora ninguna interfaz de depuración nueva.  
  
-   Las 14 interfaces de depuración que se incorporaron en .NET Framework versión 2.0 son extensiones lógicas de sus homólogas de la versión 1, e incluyen el número "2" en sus nombres.  
  
-   .NET Framework versión 3.0 y versión 3.5 usa las interfaces de .NET Framework 2.0 existentes y no incorpora ninguna interfaz nueva.  
  
-   El [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] incorpora una mezcla de versiones de la interfaz. Por ejemplo, tanto `ICorDebugThread3` como `ICorDebugThread4` aparecen como la tercera y cuarta versión de la interfaz `ICorDebugThread`. El [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] también presenta la primera versión de la `ICorDebugStackWalk` interfaz y la segunda versión de la `ICorDebugNativeFrame` interfaz (`ICorDebugNativeFrame2`).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
