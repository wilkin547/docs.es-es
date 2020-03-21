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
ms.openlocfilehash: db721e1ef774c87de0fa7da178463d832a3da756
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178156"
---
# <a name="getrequestedruntimeinfo-function"></a>GetRequestedRuntimeInfo (Función)
Obtiene información de versión y directorio sobre Common Language Runtime (CLR) solicitada por una aplicación.  
  
 Esta función ha quedado en desuso en .NET Framework 4.  
  
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
 [en] El nombre de la aplicación.  
  
 `pwszVersion`  
 [en] Cadena que especifica el número de versión del tiempo de ejecución.  
  
 `pConfigurationFile`  
 [en] El nombre del archivo de `pExe`configuración asociado a .  
  
 `startupFlags`  
 [en] Uno o varios de los valores de enumeración [STARTUP_FLAGS.](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)  
  
 `runtimeInfoFlags`  
 [en] Uno o varios de los [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) valores de enumeración.  
  
 `pDirectory`  
 [fuera] Un búfer que contiene la ruta de acceso del directorio al tiempo de ejecución una vez completado correctamente.  
  
 `dwDirectory`  
 [en] La longitud del búfer de directorio.  
  
 `dwDirectoryLength`  
 [fuera] Un puntero a la longitud de la cadena de ruta de acceso del directorio.  
  
 `pVersion`  
 [fuera] Un búfer que contiene el número de versión del tiempo de ejecución una vez completado correctamente.  
  
 `cchBuffer`  
 [en] La longitud del búfer de cadena de versión.  
  
 `dwlength`  
 [fuera] Un puntero a la longitud de la cadena de versión.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error estándar del modelo de objetos componentes (COM), tal como se define en WinError.h, además de los siguientes valores.  
  
|Código de retorno|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|ERROR_INSUFFICIENT_BUFFER|El búfer de directorio no es lo suficientemente grande como para almacenar la ruta de acceso del directorio.<br /><br /> O bien<br /><br /> El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.|  
  
## <a name="remarks"></a>Observaciones  
 El `GetRequestedRuntimeInfo` método devuelve información en tiempo de ejecución sobre la versión cargada en el proceso, que no es necesariamente la versión más reciente instalada en el equipo.  
  
 En la versión 2.0 de .NET Framework, puede obtener `GetRequestedRuntimeInfo` información sobre la última versión instalada mediante el método siguiente:  
  
- Especifique `pExe`los `pwszVersion`parámetros , , y `pConfigurationFile` null.  
  
- Especifique el indicador `RUNTIME_INFO_FLAGS` RUNTIME_INFO_UPGRADE_VERSION en `runtimeInfoFlags` las enumeraciones del parámetro.  
  
 El `GetRequestedRuntimeInfo` método no devuelve la versión más reciente de CLR en las siguientes circunstancias:  
  
- Existe un archivo de configuración de aplicación que especifica la carga de una versión CLR determinada. Tenga en cuenta que .NET Framework usará el archivo `pConfigurationFile` de configuración incluso si especifica null para el parámetro.  
  
- Se llamó al método [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) especificando una versión anterior de CLR.  
  
- Una aplicación que se compiló para una versión anterior de CLR se está ejecutando actualmente.  
  
 Para `runtimeInfoFlags` el parámetro, puede especificar solo una de `RUNTIME_INFO_FLAGS` las constantes de arquitectura de la enumeración a la vez:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MScorEE.h  
  
 **Biblioteca:** Mscoree.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [GetRequestedRuntimeVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [GetVersionFromProcess (Función)](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
