---
title: ICorDebug::CreateProcess (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: aeb39782c4c0624501a0e2a71960f5d16ab3c03e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723485"
---
# <a name="icordebugcreateprocess-method"></a>ICorDebug::CreateProcess (Método)

Inicia un proceso y su subproceso primario bajo el control del depurador.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="parameters"></a>Parámetros  

 `lpApplicationName`  
 de Puntero a una cadena terminada en null que especifica el módulo que va a ser ejecutado por el proceso iniciado. El módulo se ejecuta en el contexto de seguridad del proceso de llamada.  
  
 `lpCommandLine`  
 de Puntero a una cadena terminada en null que especifica la línea de comandos que va a ejecutar el proceso iniciado. El nombre de la aplicación (por ejemplo, "SomeApp.exe") debe ser el primer argumento.  
  
 `lpProcessAttributes`  
 de Puntero a una estructura de Win32 `SECURITY_ATTRIBUTES` que especifica el descriptor de seguridad para el proceso. Si `lpProcessAttributes` es null, el proceso obtiene un descriptor de seguridad predeterminado.  
  
 `lpThreadAttributes`  
 de Puntero a una `SECURITY_ATTRIBUTES` estructura de Win32 que especifica el descriptor de seguridad para el subproceso principal del proceso. Si `lpThreadAttributes` es null, el subproceso obtiene un descriptor de seguridad predeterminado.  
  
 `bInheritHandles`  
 de Se establece en `true` para indicar que el proceso iniciado hereda cada identificador heredable en el proceso de llamada, o `false` para indicar que no se heredan los identificadores. Los identificadores heredados tienen el mismo valor y derechos de acceso que los identificadores originales.  
  
 `dwCreationFlags`  
 de Combinación bit a bit de las [marcas de creación de procesos de Win32](/windows/win32/procthread/process-creation-flags) que controlan la clase de prioridad y el comportamiento del proceso iniciado.  
  
 `lpEnvironment`  
 de Puntero a un bloque de entorno para el nuevo proceso.  
  
 `lpCurrentDirectory`  
 de Puntero a una cadena terminada en null que especifica la ruta de acceso completa al directorio actual para el proceso. Si este parámetro es null, el nuevo proceso tendrá la misma unidad actual y el mismo directorio que el proceso que realiza la llamada.  
  
 `lpStartupInfo`  
 de Puntero a una estructura de Win32 `STARTUPINFOW` que especifica la estación de ventana, el escritorio, los identificadores estándar y la apariencia de la ventana principal del proceso iniciado.  
  
 `lpProcessInformation`  
 de Puntero a una estructura de Win32 `PROCESS_INFORMATION` que especifica la información de identificación sobre el proceso que se va a iniciar.  
  
 `debuggingFlags`  
 de Valor de la enumeración Cordebugcreateprocessflags (que especifica las opciones de depuración.  
  
 `ppProcess`  
 enuncia Puntero a la dirección de un objeto ICorDebugProcess que representa el proceso.  
  
## <a name="remarks"></a>Comentarios  

 Los parámetros de este método son los mismos que los del método Win32 `CreateProcess` .  
  
 Para habilitar la depuración en modo mixto no administrada, establezca `dwCreationFlags` en DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS. Si solo desea usar la depuración administrada, no establezca estas marcas.  
  
 Si el depurador y el proceso que se va a depurar (el proceso asociado) comparten una sola consola y se usa la depuración de interoperabilidad, es posible que el proceso asociado mantenga bloqueos de la consola y se detenga en un evento de depuración. Después, el depurador bloqueará cualquier intento de usar la consola. Para evitar este problema, establezca la marca de CREATE_NEW_CONSOLE en el `dwCreationFlags` parámetro.  
  
 No se admite la depuración de interoperabilidad en las plataformas Win9x y no x86, como las plataformas basadas en IA-64 y AMD64.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebug (Interfaz)](icordebug-interface.md)
