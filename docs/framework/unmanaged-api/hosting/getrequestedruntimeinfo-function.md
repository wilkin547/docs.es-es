---
title: GetRequestedRuntimeInfo (Función)
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
ms.openlocfilehash: cd1d9e768698115bee22e35699b044e0c3526d2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136318"
---
# <a name="getrequestedruntimeinfo-function"></a>GetRequestedRuntimeInfo (Función)
Obtiene información de la versión y del directorio sobre el Common Language Runtime (CLR) solicitado por una aplicación.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,   
    [in]  LPCWSTR  pwszVersion,   
    [in]  LPCWSTR  pConfigurationFile,   
    [in]  DWORD    startupFlags,   
    [in]  DWORD    runtimeInfoFlags,   
    [out] LPWSTR   pDirectory,   
    [in]  DWORD    dwDirectory,   
    [out] DWORD   *dwDirectoryLength,   
    [out] LPWSTR   pVersion,   
    [in]  DWORD    cchBuffer,   
    [out] DWORD   *dwlength  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pExe`  
 de El nombre de la aplicación.  
  
 `pwszVersion`  
 de Cadena que especifica el número de versión del motor en tiempo de ejecución.  
  
 `pConfigurationFile`  
 de Nombre del archivo de configuración asociado a `pExe`.  
  
 `startupFlags`  
 de Uno o varios de los valores de la enumeración [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) .  
  
 `runtimeInfoFlags`  
 de Uno o varios de los valores de la enumeración [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) .  
  
 `pDirectory`  
 enuncia Un búfer que contiene la ruta de acceso al directorio al tiempo de ejecución cuando se completa correctamente.  
  
 `dwDirectory`  
 de Longitud del búfer de directorio.  
  
 `dwDirectoryLength`  
 enuncia Puntero a la longitud de la cadena de ruta de acceso del directorio.  
  
 `pVersion`  
 enuncia Un búfer que contiene el número de versión del motor en tiempo de ejecución cuando se completa correctamente.  
  
 `cchBuffer`  
 de Longitud del búfer de cadena de versión.  
  
 `dwlength`  
 enuncia Puntero a la longitud de la cadena de versión.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|ERROR_INSUFFICIENT_BUFFER|El búfer de directorio no es lo suficientemente grande como para almacenar la ruta de acceso al directorio.<br /><br /> O bien<br /><br /> El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.|  
  
## <a name="remarks"></a>Comentarios  
 El método `GetRequestedRuntimeInfo` devuelve información en tiempo de ejecución sobre la versión cargada en el proceso, que no es necesariamente la versión más reciente instalada en el equipo.  
  
 En la versión .NET Framework 2,0, puede obtener información sobre la última versión instalada mediante el método `GetRequestedRuntimeInfo` de la siguiente manera:  
  
- Especifique los parámetros `pExe`, `pwszVersion`y `pConfigurationFile` como null.  
  
- Especifique la marca RUNTIME_INFO_UPGRADE_VERSION en las enumeraciones de `RUNTIME_INFO_FLAGS` para el parámetro `runtimeInfoFlags`.  
  
 El método `GetRequestedRuntimeInfo` no devuelve la última versión de CLR en las siguientes circunstancias:  
  
- Existe un archivo de configuración de la aplicación que especifica la carga de una determinada versión de CLR. Tenga en cuenta que la .NET Framework usará el archivo de configuración aunque especifique NULL para el parámetro `pConfigurationFile`.  
  
- Se llamó al método [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) especificando una versión anterior de CLR.  
  
- Se está ejecutando una aplicación que se compiló para una versión anterior de CLR.  
  
 En el caso del parámetro `runtimeInfoFlags`, solo puede especificar una de las constantes de la arquitectura de la enumeración `RUNTIME_INFO_FLAGS` a la vez:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetRequestedRuntimeVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [GetVersionFromProcess (Función)](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
