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
ms.openlocfilehash: b120b854e1787824808dd64d95b0fa78ba6c9fa2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705493"
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
 de Nombre del archivo de configuración que está asociado a `pExe` .  
  
 `startupFlags`  
 de Uno o varios de los valores de enumeración de [STARTUP_FLAGS](startup-flags-enumeration.md) .  
  
 `runtimeInfoFlags`  
 de Uno o varios de los valores de enumeración de [RUNTIME_INFO_FLAGS](runtime-info-flags-enumeration.md) .  
  
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
|ERROR_INSUFFICIENT_BUFFER|El búfer de directorio no es lo suficientemente grande como para almacenar la ruta de acceso al directorio.<br /><br /> o bien<br /><br /> El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.|  
  
## <a name="remarks"></a>Comentarios  

 El `GetRequestedRuntimeInfo` método devuelve información en tiempo de ejecución sobre la versión cargada en el proceso, que no es necesariamente la versión más reciente instalada en el equipo.  
  
 En la versión .NET Framework 2,0, puede obtener información sobre la última versión instalada mediante el método de la `GetRequestedRuntimeInfo` siguiente manera:  
  
- Especifique los `pExe` `pwszVersion` parámetros, y `pConfigurationFile` como null.  
  
- Especifique el marcador de RUNTIME_INFO_UPGRADE_VERSION en las `RUNTIME_INFO_FLAGS` enumeraciones para el `runtimeInfoFlags` parámetro.  
  
 El `GetRequestedRuntimeInfo` método no devuelve la última versión de CLR en las siguientes circunstancias:  
  
- Existe un archivo de configuración de la aplicación que especifica la carga de una determinada versión de CLR. Tenga en cuenta que la .NET Framework usará el archivo de configuración aunque especifique NULL para el `pConfigurationFile` parámetro.  
  
- Se llamó al método [CorBindToRuntimeEx](corbindtoruntimeex-function.md) especificando una versión anterior de CLR.  
  
- Se está ejecutando una aplicación que se compiló para una versión anterior de CLR.  
  
 Para el `runtimeInfoFlags` parámetro, solo puede especificar una de las constantes de arquitectura de la `RUNTIME_INFO_FLAGS` enumeración a la vez:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [GetRequestedRuntimeVersion (Función)](getrequestedruntimeversion-function.md)
- [GetVersionFromProcess (Función)](getversionfromprocess-function.md)
- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
