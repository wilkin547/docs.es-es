---
title: ICorDebug::CreateProcess (Método)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- ICorDebug.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type:
- apiref
caps.latest.revision: 21
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 16e45f3bad92914ce8c7fb0044534789a7a28b2e
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/10/2018
---
# <a name="icordebugcreateprocess-method"></a>ICorDebug::CreateProcess (Método)
Inicia un proceso y su subproceso principal bajo el control del depurador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateProcess (  
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
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `lpApplicationName`  
 [in] Puntero a una cadena terminada en null que especifica el módulo que va a ejecutar el proceso iniciado. El módulo se ejecuta en el contexto de seguridad del proceso que realiza la llamada.  
  
 `lpCommandLine`  
 [in] Puntero a una cadena terminada en null que especifica la línea de comandos que va a ejecutar el proceso iniciado. El nombre de la aplicación (por ejemplo, "SomeApp.exe") debe ser el primer argumento.  
  
 `lpProcessAttributes`  
 [in] Puntero a Win32 `SECURITY_ATTRIBUTES` estructura que especifica el descriptor de seguridad para el proceso. Si `lpProcessAttributes` es null, el proceso obtiene un descriptor de seguridad predeterminado.  
  
 `lpThreadAttributes`  
 [in] Puntero a Win32 `SECURITY_ATTRIBUTES` estructura que especifica el descriptor de seguridad para el subproceso principal del proceso. Si `lpThreadAttributes` es null, el subproceso obtiene un descriptor de seguridad predeterminado.  
  
 `bInheritHandles`  
 [in] Establecido en `true` para indicar que el proceso iniciado, heredan todos los identificadores heredables en el proceso de llamada o `false` para indicar que no se heredan los identificadores. Los identificadores heredados tienen el mismo valor y derechos de acceso que los identificadores originales.  
  
 `dwCreationFlags`  
 [in] Una combinación bit a bit de los [marcas de creación de proceso Win32](http://go.microsoft.com/fwlink/?linkid=69981) que controlan la clase de prioridad y el comportamiento del proceso iniciado.  
  
 `lpEnvironment`  
 [in] Puntero a un bloque de entorno para el nuevo proceso.  
  
 `lpCurrentDirectory`  
 [in] Puntero a una cadena terminada en null que especifica la ruta de acceso completa al directorio actual para el proceso. Si este parámetro es null, el nuevo proceso tendrá la misma unidad y directorio actuales que el proceso que realiza la llamada.  
  
 `lpStartupInfo`  
 [in] Puntero a Win32 `STARTUPINFOW` estructura que especifica la estación de ventana, escritorio, los identificadores estándares y apariencia de la ventana principal para el proceso iniciado.  
  
 `lpProcessInformation`  
 [in] Puntero a Win32 `PROCESS_INFORMATION` estructura que especifica la información de identificación sobre el proceso que se iniciará.  
  
 `debuggingFlags`  
 [in] Un valor de la enumeración CorDebugCreateProcessFlags que especifica las opciones de depuración.  
  
 `ppProcess`  
 [out] Un puntero a la dirección de un objeto ICorDebugProcess que representa el proceso.  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros de este método son los mismos que los de Win32 `CreateProcess` método.  
  
 Para habilitar la depuración en modo mixto no administrada, establezca `dwCreationFlags` en DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS. Si desea usar solo la depuración administrada, no establezca estos indicadores.  
  
 Si el depurador y el proceso de depuran (el proceso asociado) comparten una única consola, y si se utiliza la depuración de interoperabilidad, es posible que el proceso asociado contener los bloqueos de la consola y dejar a un evento de depuración. El depurador, a continuación, bloqueará cualquier intento de usar la consola. Para evitar este problema, establezca el marcador CREATE_NEW_CONSOLE el `dwCreationFlags` parámetro.  
  
 No se admite la depuración de interoperabilidad en plataformas Win9x y no x86 como plataformas basadas en IA-64 y AMD64-based.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
