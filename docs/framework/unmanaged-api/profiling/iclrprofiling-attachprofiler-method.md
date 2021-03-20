---
description: 'Más información sobre: ICLRProfiling:: AttachProfiler (método)'
title: ICLRProfiling::AttachProfiler (Método)
ms.date: 03/30/2017
api_name:
- IClrProfiling.AttachProfiler Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- IClrProfiling::AttachProfiler
helpviewer_keywords:
- AttachProfiler method [.NET Framework profiling]
- IClrProfiling::AttachProfiler method [.NET Framework profiling]
ms.assetid: 535a6839-c443-405b-a6f4-e2af90725d5b
topic_type:
- apiref
ms.openlocfilehash: 00ae5ca76462d8800a77c2869ef73703a4f1d980
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760774"
---
# <a name="iclrprofilingattachprofiler-method"></a>ICLRProfiling::AttachProfiler (Método)

Asocia el generador de perfiles especificado al proceso especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AttachProfiler(  
  [in] DWORD dwProfileeProcessID,  
  [in] DWORD dwMillisecondsMax,                     // optional  
  [in] const CLSID * pClsidProfiler,  
  [in] LPCWSTR wszProfilerPath,                     // optional  
  [in] size_is(cbClientData)] void * pvClientData,  // optional  
  [in] UINT cbClientData);                          // optional  
```  
  
## <a name="parameters"></a>Parámetros

`dwProfileeProcessID` de IDENTIFICADOR de proceso del proceso al que se debe adjuntar el generador de perfiles. En un equipo de 64 bits, el valor de bits del proceso cuyo perfil se ha generado debe coincidir con el valor de bits del proceso desencadenador que llama a `AttachProfiler`. Si la cuenta de usuario con la que llama a `AttachProfiler` tiene privilegios administrativos, el proceso de destino puede ser cualquier proceso del sistema. De lo contrario, el proceso de destino debe pertenecer a la misma cuenta de usuario.

`dwMillisecondsMax` de Tiempo, en milisegundos, para `AttachProfiler` que se complete. El proceso de desencadenador debe pasar un tiempo de espera que se sabe que es suficiente para que el generador de perfiles determinado complete su inicialización.
  
`pClsidProfiler` de Puntero al CLSID del generador de perfiles que se va a cargar. El proceso desencadenador puede reutilizar esta memoria después de que `AttachProfiler` vuelva.

`wszProfilerPath` de Ruta de acceso completa al archivo DLL del generador de perfiles que se va a cargar. Esta cadena debe contener un máximo de 260 caracteres, incluido el terminador NULL. Si `wszProfilerPath` es NULL o una cadena vacía, Common Language Runtime (CLR) intentará encontrar la ubicación del archivo DLL del generador de perfiles; para ello, buscará en el Registro el CLSID al que `pClsidProfiler` apunta.

`pvClientData` de Puntero a los datos que se van a pasar al generador de perfiles mediante el método [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) . El proceso desencadenador puede reutilizar esta memoria después de que `AttachProfiler` vuelva. Si `pvClientData` es NULL, `cbClientData` debe ser 0 (cero).

`cbClientData` de Tamaño, en bytes, de los datos a los que `pvClientData` señala.

## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los HRESULT siguientes.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El generador de perfiles especificado se ha asociado correctamente al proceso de destino.|  
|CORPROF_E_PROFILER_ALREADY_ACTIVE|Ya hay un generador de perfiles activo o asociado al proceso de destino.|  
|CORPROF_E_PROFILER_NOT_ATTACHABLE|El generador de perfiles especificado no admite la asociación. El proceso desencadenador puede intentar asociar un generador de perfiles diferente.|  
|CORPROF_E_PROFILEE_INCOMPATIBLE_WITH_TRIGGER|No puede solicitar la asociación de un generador de perfiles porque la versión del proceso de destino es incompatible con el proceso actual que está llamando a `AttachProfiler`.|  
|HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED)|El usuario del proceso desencadenador no tiene acceso al proceso de destino.|  
|HRESULT_FROM_WIN32(ERROR_PRIVILEGE_NOT_HELD)|El usuario del proceso desencadenador no tiene los privilegios necesarios para asociar un generador de perfiles al proceso de destino especificado. El registro de eventos de aplicación puede contener más información.|  
|CORPROF_E_IPC_FAILED|Se produjo un error de comunicación con el proceso de destino. Esto suele ocurrir si el proceso de destino se estaba cerrando.|  
|HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND)|El proceso de destino no existe o no está ejecutando ningún CLR que admita la asociación. Esto puede indicar que el CLR se descargó desde la llamada al método de enumeración en tiempo de ejecución.|  
|HRESULT_FROM_WIN32(ERROR_TIMEOUT)|El tiempo de espera se agotó sin que el generador de perfiles comenzara a cargarse. Puede volver a intentar la operación de asociación. El tiempo de espera se agota cuando un finalizador del proceso de destino se ejecuta durante más tiempo que el valor del tiempo de espera.|  
|E_INVALIDARG|Uno o más parámetros tienen valores no válidos.|  
|E_FAIL|Se ha producido algún otro error no especificado.|  
|Otros códigos de error|Si el método [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) del generador de perfiles devuelve un valor HRESULT que indica un error, `AttachProfiler` devuelve el mismo HRESULT. En este caso, E_NOTIMPL se convierte en CORPROF_E_PROFILER_NOT_ATTACHABLE.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="memory-management"></a>Administración de memoria  

 En consonancia con las convenciones de COM, el llamador de `AttachProfiler` (por ejemplo, el código desencadenador creado por el desarrollador del generador de perfiles) es responsable de la asignación y desasignación de la memoria para los datos a los que el parámetro `pvClientData` apunta. Cuando el CLR ejecuta la llamada a `AttachProfiler`, realiza una copia de la memoria a la que `pvClientData` apunta y la transmite al proceso de destino. Cuando el CLR dentro del proceso de destino recibe su propia copia del bloque `pvClientData`, pasa el bloque al generador de perfiles con el método `InitializeForAttach` y, después, desasigna su copia del bloque `pvClientData` del proceso de destino.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerInfo3 (Interfaz)](icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
