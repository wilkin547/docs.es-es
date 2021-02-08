---
description: 'Más información sobre: ICorDebugRemote:: Createprocessex ((método)'
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
ms.openlocfilehash: cd27400f5c9f348621fb66b3b7730cf15d397151
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794733"
---
# <a name="icordebugremotecreateprocessex-method"></a>ICorDebugRemote::CreateProcessEx (Método)

Inicia un proceso en un equipo remoto en el depurador.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="parameters"></a>Parámetros  

 `pRemoteTarget`  
 de Puntero a una [interfaz ICorDebugRemoteTarget](icordebugremotetarget-interface.md). Se utiliza para determinar el equipo remoto en el que se va a iniciar el proceso.  
  
 `lpApplicationName`  
 de Puntero a una cadena terminada en null que especifica el módulo que va a ser ejecutado por el proceso iniciado. El módulo se ejecuta en el contexto de seguridad del proceso de llamada.  
  
 `lpCommandLine`  
 de Puntero a una cadena terminada en null que especifica la línea de comandos que va a ejecutar el proceso iniciado.  
  
 `lpProcessAttributes`  
 de No se usa para la depuración remota.  
  
 `lpThreadAttributes`  
 de No se usa para la depuración remota.  
  
 `bInheritHandles`  
 de No se usa para la depuración remota.  
  
 `dwCreationFlags`  
 de No se usa para la depuración remota.  
  
 `lpEnvironment`  
 de Puntero a un bloque de entorno para el nuevo proceso.  
  
 `lpCurrentDirectory`  
 de Puntero a una cadena terminada en null que especifica la ruta de acceso completa al directorio actual para el proceso. Si este parámetro es null, el nuevo proceso tendrá la misma unidad actual y el mismo directorio que el proceso que realiza la llamada.  
  
 `lpStartupInfo`  
 de No se usa para la depuración remota.  
  
 `lpProcessInformation`  
 de No se usa para la depuración remota.  
  
 `debuggingFlags`  
 de No se usa para la depuración remota.  
  
 `ppProcess`  
 enuncia Puntero a la dirección de un objeto "ICorDebugProcess interface" que representa el proceso.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK  
 Inició correctamente el proceso en el equipo remoto y devolvió una "ICorDebugProcess interface" para la depuración.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 No se puede iniciar el proceso en el equipo remoto y devolver una "ICorDebugProcess interface" para la depuración.  
  
## <a name="remarks"></a>Observaciones  

 En Silverlight no se admite la depuración en modo mixto.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>Vea también

- [ICorDebugRemote (Interfaz)](icordebugremote-interface.md)
- [ICorDebug (Interfaz)](icordebug-interface.md)

- [Interfaces para depuración](debugging-interfaces.md)
