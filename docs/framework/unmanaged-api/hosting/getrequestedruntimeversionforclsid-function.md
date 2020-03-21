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
ms.openlocfilehash: 6132e94544b30486b70ecfec49c1ddd5e3c0f50b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178118"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID (Función)
Obtiene la información de versión de Common Language Runtime `CLSID`(CLR) adecuada para la clase con el archivo .  
  
 Esta función ha quedado en desuso en .NET Framework 4.  
  
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
 [en]  El `CLSID` componente.  
  
 `pVersion`  
 [fuera]  Un búfer que contiene la cadena de número de versión una vez completado correctamente.  
  
 `cchBuffer`  
 [en]  El tamaño, en caracteres `pVersion` anchos, del búfer.  
  
 `dwLength`  
 [fuera] La longitud, en bytes, del búfer devuelto.  
  
 `dwResolutionFlags`  
 [en]  Uno de los valores CLSID_RESOLUTION_FLAGS. Se admiten los valores siguientes:  
  
- CLSID_RESOLUTION_DEFAULT: (0x0) Especifica que se debe utilizar el comportamiento de interoperabilidad predeterminado.  
  
- CLSID_RESOLUTION_REGISTERED: (0x1) Especifica que se debe buscar en el registro y aplicar la directiva de correcciones de archivos.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La función se devolvió correctamente.|  
|E_INVALIDARG|Uno de los parámetros tiene un tipo o formato no válido.|  
|ERROR_INSUFFICIENT_BUFFER|El `pVersion` búfer no es lo suficientemente grande como para contener toda la cadena de versión.|  
|REGDB_E_CLASSNOTREG|No hay ninguna clase registrada `CLSID`con el archivo .|  
|E_POINTER|`dwLength`es null, `cchBuffer` o es lo suficientemente `pVersion` grande como para contener la cadena de versión, pero es null.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MScorEE.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
