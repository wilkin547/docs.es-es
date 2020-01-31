---
title: ICorProfilerInfo4 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
ms.openlocfilehash: c287b630aee58c6795ef405cc1801149e220fd51
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868426"
---
# <a name="icorprofilerinfo4-interface"></a>ICorProfilerInfo4 (Interfaz)
Proporciona métodos que los perfiles de código usan para comunicarse con el Common Language Runtime (CLR) para controlar la supervisión de eventos y la información de la solicitud. . La interfaz de `ICorProfilerInfo4` es una extensión de las otras interfaces de `ICorProfilerInfo`. Proporciona nuevos métodos para admitir la recompilación Just-in-Time (JIT), agregada en el .NET Framework 4,5.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumJITedFunctions2 (método)](icorprofilerinfo4-enumjitedfunctions2-method.md)|Devuelve un enumerador para todas las funciones compiladas previamente y compiladas con JIT.|  
|[EnumThreads (método)](icorprofilerinfo4-enumthreads-method.md)|Obtiene un enumerador que proporciona métodos para recorrer secuencialmente en iteración la colección de todos los subprocesos administrados en el proceso de la que se van a realizar perfiles.|  
|[GetCodeInfo3 (método)](icorprofilerinfo4-getcodeinfo3-method.md)|Obtiene las extensiones de código nativo asociadas con la versión recompilada con JIT de la función especificada.|  
|[GetFunctionFromIP2 (método)](icorprofilerinfo4-getfunctionfromip2-method.md)|Asigna un puntero de instrucción de código administrado a la versión recompilada con JIT de una función especificada.|  
|[GetILToNativeMapping2 (método)](icorprofilerinfo4-getiltonativemapping2-method.md)|Obtiene una asignación de los desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos para el código contenido en la versión recompilada con JIT de la función especificada.|  
|[GetObjectSize2 (método)](icorprofilerinfo4-getobjectsize2-method.md)|Devuelve el tamaño de un objeto especificado.|  
|[GetReJITIDs (método)](icorprofilerinfo4-getrejitids-method.md)|Devuelve una matriz de identificadores que identifican todas las versiones compiladas con JIT de la función especificada que se siguen asignando.|  
|[InitializeCurrentThread (método)](icorprofilerinfo4-initializecurrentthread-method.md)|Inicializa el subproceso actual antes de las llamadas posteriores a la API del generador de perfiles en el mismo subproceso, de modo que se pueda evitar el interbloqueo.|  
|[RequestReJIT (método)](icorprofilerinfo4-requestrejit-method.md)|Solicita una recompilación con JIT de todas las instancias de las funciones especificadas.|  
|[RequestRevert (método)](icorprofilerinfo4-requestrevert-method.md)|Revierte todas las instancias de las funciones especificadas a sus versiones originales.|  
  
## <a name="remarks"></a>Notas  
 El CLR implementa los métodos de la interfaz `ICorProfilerInfo4` usando el modelo de subprocesamiento libre. Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo. Para obtener una lista de los posibles códigos devueltos, consulte el archivo CorError.h.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)
