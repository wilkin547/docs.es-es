---
title: GetVersionFromProcess (Función)
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
ms.openlocfilehash: da0d159da6eef7745c1fa7f7320d5e1355f6e413
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721886"
---
# <a name="getversionfromprocess-function"></a>GetVersionFromProcess (Función)

Obtiene el número de versión del Common Language Runtime (CLR) que está asociado al identificador de proceso especificado.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `hProcess`  
 de Identificador de un proceso.  
  
 `pVersion`  
 enuncia Un búfer que contiene la cadena del número de versión cuando se completa correctamente el método.  
  
 `cchBuffer`  
 de Longitud del búfer de versión.  
  
 `pdwLength`  
 enuncia Puntero a la longitud de la cadena del número de versión.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`pVersion` es NULL y `cchBuffer` no es null, o viceversa.<br /><br /> o bien<br /><br /> `hProcess` no es un identificador válido para un proceso.<br /><br /> o bien<br /><br /> CLR no está cargado.|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer` es null o menor que la longitud de la cadena de versión.|  
|E_NOTIMPL|Este método no está disponible en el sistema operativo Microsoft Windows 95, Microsoft Windows 98 o Microsoft Windows Millennium Edition.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [GetRequestedRuntimeInfo (Función)](getrequestedruntimeinfo-function.md)
- [GetRequestedRuntimeVersion (Función)](getrequestedruntimeversion-function.md)
- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
