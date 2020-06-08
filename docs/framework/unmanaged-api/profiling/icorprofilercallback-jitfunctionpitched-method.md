---
title: ICorProfilerCallback::JITFunctionPitched (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
ms.openlocfilehash: 2715a5b6b03a5ad33a6f18fb736fce3911bfbef0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500031"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>ICorProfilerCallback::JITFunctionPitched (Método)
Notifica al generador de perfiles que se ha quitado de la memoria una función que se ha compilado Just-in-Time (JIT).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a>Parámetros  
 `functionId`  
 de IDENTIFICADOR de la función que se ha quitado.  
  
## <a name="remarks"></a>Comentarios  
 Si se llama a la función que se quita, el generador de perfiles recibirá nuevos eventos de compilación JIT cuando se vuelva a compilar la función. Actualmente, el compilador JIT de Common Language Runtime (CLR) no quita funciones de la memoria, por lo que esta devolución de llamada no se utiliza actualmente y el generador de perfiles no las recibirá.  
  
 El valor de `functionId` no es válido hasta que se vuelva a compilar la función. Cuando se vuelva a compilar la función, se usará el mismo `functionId` valor.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
