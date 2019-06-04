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
ms.openlocfilehash: 0ca125932ede48aa43bc51e3d5a7851fb7762547
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490320"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID (Función)
Obtiene la correspondiente información common language runtime (CLR) versión para la clase con los valores especificados `CLSID`.  
  
 Esta función está desusada en .NET Framework 4.  
  
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
  
## <a name="parameters"></a>Parámetros  
 `rclsid`  
 [in]  El `CLSID` del componente.  
  
 `pVersion`  
 [out]  Un búfer que contiene la cadena de número de versión tras completarse correctamente.  
  
 `cchBuffer`  
 [in]  El tamaño, en caracteres anchos, de la `pVersion` búfer.  
  
 `dwLength`  
 [out] La longitud, en bytes, del búfer devuelto.  
  
 `dwResolutionFlags`  
 [in]  Uno de los valores CLSID_RESOLUTION_FLAGS. Se admiten los siguientes valores:  
  
- CLSID_RESOLUTION_DEFAULT: (0 x 0) especifica que debe usarse el comportamiento de interoperabilidad predeterminado.  
  
- CLSID_RESOLUTION_REGISTERED: (0 x 1) especifica que se debe buscar el registro y se debe aplicar la directiva de correcciones de compatibilidad.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La función se devolvió correctamente.|  
|E_INVALIDARG|Uno de los parámetros tiene un formato o tipo no válido.|  
|ERROR_INSUFFICIENT_BUFFER|El `pVersion` búfer no es lo suficientemente grande como para contener la cadena de versión completa.|  
|REGDB_E_CLASSNOTREG|No hay ninguna clase registrada con los valores especificados `CLSID`.|  
|E_POINTER|`dwLength` es null, o `cchBuffer` es lo suficientemente grande como para contener la cadena de versión, pero `pVersion` es null.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
