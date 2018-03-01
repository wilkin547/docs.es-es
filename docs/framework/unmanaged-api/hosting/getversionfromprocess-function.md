---
title: "GetVersionFromProcess (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db5054ab9b71eb93005fc0315acba82d807487ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getversionfromprocess-function"></a>GetVersionFromProcess (Función)
Obtiene el número de versión de common language runtime (CLR) que está asociado con el identificador de proceso especificado.  
  
 Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `hProcess`  
 [in] Un identificador de proceso.  
  
 `pVersion`  
 [out] Un búfer que contiene la cadena del número de versión en la realización correcta del método.  
  
 `cchBuffer`  
 [in] La longitud del búfer de versión.  
  
 `pdwLength`  
 [out] Un puntero a la longitud de la cadena del número de versión.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error estándar de modelo de objetos componentes (COM), como se define en WinError.h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`pVersion`es null y `cchBuffer` no es null, o viceversa.<br /><br /> O bien<br /><br /> `hProcess`no es un identificador válido para un proceso.<br /><br /> O bien<br /><br /> El CLR no está cargado.|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer`es nulo o menor que la longitud de la cadena de versión.|  
|E_NOTIMPL|Este método no está disponible en el sistema operativo Microsoft Windows 95, Microsoft Windows 98 o Microsoft Windows Millennium Edition.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [GetRequestedRuntimeInfo (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [GetRequestedRuntimeVersion (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
