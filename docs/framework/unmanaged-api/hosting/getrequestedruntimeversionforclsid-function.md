---
title: GetRequestedRuntimeVersionForCLSID (Función)
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8d3a7168ce0ee3484384ae0e2d10ca00367fc9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID (Función)
Obtiene la correspondiente información common language runtime (CLR) versión para la clase con los valores especificados `CLSID`.  
  
 Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `rclsid`  
 [in]  El `CLSID` del componente.  
  
 `pVersion`  
 [out]  Un búfer que contiene la cadena del número de versión en la realización correcta.  
  
 `cchBuffer`  
 [in]  El tamaño, en caracteres anchos, de la `pVersion` búfer.  
  
 `dwLength`  
 [out] La longitud, en bytes, del búfer devuelto.  
  
 `dwResolutionFlags`  
 [in]  Uno de los valores CLSID_RESOLUTION_FLAGS. Se admiten los siguientes valores:  
  
-   CLSID_RESOLUTION_DEFAULT: (0 x 0) especifica ese comportamiento de interoperabilidad predeterminado debe ser utilizado.  
  
-   CLSID_RESOLUTION_REGISTERED: (0 x 1) especifica que el registro se debe buscar y correcciones de compatibilidad de directiva debe ser aplicado.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La función se devolvió correctamente.|  
|E_INVALIDARG|Uno de los parámetros tiene un formato o un tipo no válido.|  
|ERROR_INSUFFICIENT_BUFFER|El `pVersion` búfer no es lo suficientemente grande como para contener la cadena de versión completo.|  
|REGDB_E_CLASSNOTREG|No hay ninguna clase registrada con los valores especificados `CLSID`.|  
|E_POINTER|`dwLength` es null, o `cchBuffer` es lo suficientemente grande como para contener la cadena de versión, pero `pVersion` es null.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
