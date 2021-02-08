---
description: 'Más información acerca de: GetRequestedRuntimeVersionForCLSID ((función)'
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
ms.openlocfilehash: 10fdc947181d3f1fa12b33f11cf31b68fc4285cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785268"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID (Función)

Obtiene la información de versión de Common Language Runtime (CLR) adecuada para la clase con el especificado `CLSID` .  
  
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
 de  `CLSID` Del componente.  
  
 `pVersion`  
 enuncia  Un búfer que contiene la cadena del número de versión cuando se completa correctamente.  
  
 `cchBuffer`  
 de  Tamaño, en caracteres anchos, del `pVersion` búfer.  
  
 `dwLength`  
 enuncia La longitud, en bytes, del búfer devuelto.  
  
 `dwResolutionFlags`  
 de  Uno de los valores de CLSID_RESOLUTION_FLAGS. Se admiten los valores siguientes:  
  
- CLSID_RESOLUTION_DEFAULT: (0X0) especifica que debe usarse el comportamiento predeterminado de interoperabilidad.  
  
- CLSID_RESOLUTION_REGISTERED: (0x1) especifica que se debe buscar en el registro y que se aplique la Directiva de correcciones de compatibilidad (shim).  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La función se devolvió correctamente.|  
|E_INVALIDARG|Uno de los parámetros tiene un tipo o formato no válido.|  
|ERROR_INSUFFICIENT_BUFFER|El `pVersion` búfer no es suficientemente grande para contener la cadena de versión completa.|  
|REGDB_E_CLASSNOTREG|No hay ninguna clase registrada con el especificado `CLSID` .|  
|E_POINTER|`dwLength` es null, o `cchBuffer` es lo suficientemente grande como para contener la cadena de versión, pero `pVersion` es NULL.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
