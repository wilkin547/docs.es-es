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
ms.openlocfilehash: ce0c6307defd93dcf63ac4e9051fc798041475f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127054"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID (Función)
Obtiene la información de versión de Common Language Runtime (CLR) adecuada para la clase con el `CLSID`especificado.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de  `CLSID` del componente.  
  
 `pVersion`  
 enuncia  Un búfer que contiene la cadena del número de versión cuando se completa correctamente.  
  
 `cchBuffer`  
 de  Tamaño, en caracteres anchos, del búfer `pVersion`.  
  
 `dwLength`  
 enuncia La longitud, en bytes, del búfer devuelto.  
  
 `dwResolutionFlags`  
 de  Uno de los valores de CLSID_RESOLUTION_FLAGS. Se admiten los siguientes valores:  
  
- CLSID_RESOLUTION_DEFAULT: (0X0) especifica que debe usarse el comportamiento predeterminado de interoperabilidad.  
  
- CLSID_RESOLUTION_REGISTERED: (0x1) especifica que se debe buscar en el registro y que se aplique la Directiva de correcciones de compatibilidad (shim).  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La función se devolvió correctamente.|  
|E_INVALIDARG|Uno de los parámetros tiene un tipo o formato no válido.|  
|ERROR_INSUFFICIENT_BUFFER|El búfer `pVersion` no es suficientemente grande para contener la cadena de versión completa.|  
|REGDB_E_CLASSNOTREG|No hay ninguna clase registrada con el `CLSID`especificado.|  
|E_POINTER|`dwLength` es null, o `cchBuffer` es lo suficientemente grande como para contener la cadena de versión, pero `pVersion` es NULL.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
