---
title: ICorDebugRemote::CreateProcessEx (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06bdc3605d981acad68a97901627f361da4061c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugremotecreateprocessex-method"></a>ICorDebugRemote::CreateProcessEx (Método)
Inicia un proceso en un equipo remoto en el depurador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pRemoteTarget`  
 [in] Puntero a un [ICorDebugRemoteTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md). Se utiliza para determinar el equipo remoto en el que se va a iniciar el proceso.  
  
 `lpApplicationName`  
 [in] Puntero a una cadena terminada en null que especifica el módulo que va a ejecutar el proceso iniciado. El módulo se ejecuta en el contexto de seguridad del proceso que realiza la llamada.  
  
 `lpCommandLine`  
 [in] Puntero a una cadena terminada en null que especifica la línea de comandos que va a ejecutar el proceso iniciado.  
  
 `lpProcessAttributes`  
 [in] No se utiliza para la depuración remota.  
  
 `lpThreadAttributes`  
 [in] No se utiliza para la depuración remota.  
  
 `bInheritHandles`  
 [in] No se utiliza para la depuración remota.  
  
 `dwCreationFlags`  
 [in] No se utiliza para la depuración remota.  
  
 `lpEnvironment`  
 [in] Puntero a un bloque de entorno para el nuevo proceso.  
  
 `lpCurrentDirectory`  
 [in] Puntero a una cadena terminada en null que especifica la ruta de acceso completa al directorio actual para el proceso. Si este parámetro es null, el nuevo proceso tendrá la misma unidad y directorio actuales que el proceso que realiza la llamada.  
  
 `lpStartupInfo`  
 [in] No se utiliza para la depuración remota.  
  
 `lpProcessInformation`  
 [in] No se utiliza para la depuración remota.  
  
 `debuggingFlags`  
 [in] No se utiliza para la depuración remota.  
  
 `ppProcess`  
 [out] Un puntero a la dirección de un objeto de "ICorDebugProcess (interfaz)" que representa el proceso.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 Iniciar correctamente el proceso en el equipo remoto y devuelve un "ICorDebugProcess (interfaz)" para la depuración.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 No se puede iniciar el proceso en el equipo remoto y devolver un "ICorDebugProcess (interfaz)" para la depuración.  
  
## <a name="remarks"></a>Comentarios  
 No se admite la depuración en modo mixto en Silverlight.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugRemote (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
