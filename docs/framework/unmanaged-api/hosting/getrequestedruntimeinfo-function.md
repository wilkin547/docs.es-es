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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f37be8e3d2e92147e9f13954ab64396062ade2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="getrequestedruntimeinfo-function"></a>GetRequestedRuntimeInfo (Función)
Obtiene información de versión y directorio sobre solicitado por una aplicación de common language runtime (CLR).  
  
 Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
#### <a name="parameters"></a>Parámetros  
 `pExe`  
 [in] El nombre de la aplicación.  
  
 `pwszVersion`  
 [in] Cadena que especifica el número de versión del runtime.  
  
 `pConfigurationFile`  
 [in] El nombre del archivo de configuración que está asociado a `pExe`.  
  
 `startupFlags`  
 [in] Uno o varios de los [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) valores de enumeración.  
  
 `runtimeInfoFlags`  
 [in] Uno o varios de los [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) valores de enumeración.  
  
 `pDirectory`  
 [out] Un búfer que contiene la ruta del directorio para el tiempo de ejecución una vez completada correctamente.  
  
 `dwDirectory`  
 [in] La longitud del búfer de directorio.  
  
 `dwDirectoryLength`  
 [out] Un puntero a la longitud de la cadena de ruta de acceso de directorio.  
  
 `pVersion`  
 [out] Un búfer que contiene el número de versión del tiempo de ejecución una vez completada correctamente.  
  
 `cchBuffer`  
 [in] La longitud del búfer de cadena de versión.  
  
 `dwlength`  
 [out] Un puntero a la longitud de la cadena de versión.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error estándar de modelo de objetos componentes (COM), como se define en WinError.h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|ERROR_INSUFFICIENT_BUFFER|El búfer de directorio no es lo suficientemente grande como para almacenar la ruta de acceso de directorio.<br /><br /> O bien<br /><br /> El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.|  
  
## <a name="remarks"></a>Comentarios  
 El `GetRequestedRuntimeInfo` método devuelve información de tiempo de ejecución sobre la versión que se cargan en el proceso, que no es necesariamente la última versión instalada en el equipo.  
  
 En la versión 2.0 de .NET Framework, puede obtener información acerca de la última versión instalada mediante la `GetRequestedRuntimeInfo` método tal como se indica a continuación:  
  
-   Especifique el `pExe`, `pwszVersion`, y `pConfigurationFile` parámetros como null.  
  
-   Especifique el marcador RUNTIME_INFO_UPGRADE_VERSION en el `RUNTIME_INFO_FLAGS` enumeraciones para el `runtimeInfoFlags` parámetro.  
  
 El `GetRequestedRuntimeInfo` método no devuelve la última versión CLR en las circunstancias siguientes:  
  
-   Existe un archivo de configuración que especifica que debe cargarse una determinada versión CLR. Tenga en cuenta que .NET Framework utilizará el archivo de configuración incluso si se especifica null para la `pConfigurationFile` parámetro.  
  
-   El [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) método se llamó especificando una versión anterior de CLR.  
  
-   Una aplicación que se compiló para una versión anterior de CLR se está ejecutando actualmente.  
  
 Para el `runtimeInfoFlags` parámetro, puede especificar sólo una de las constantes de arquitectura de la `RUNTIME_INFO_FLAGS` enumeración a la vez:  
  
-   RUNTIME_INFO_REQUEST_IA64  
  
-   RUNTIME_INFO_REQUEST_AMD64  
  
-   RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [GetRequestedRuntimeVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [GetVersionFromProcess (Función)](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
