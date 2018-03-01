---
title: "GetCORVersion (Función)"
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
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c61dd0b10bc0229d8f0d7dd4f6357ddaf5986637
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getcorversion-function"></a>GetCORVersion (Función)
Devuelve el número de versión de common language runtime (CLR) que se ejecuta en el proceso actual.  
  
 Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a>Parámetros  
 `pbuffer`  
 Un puntero a un búfer en el que CLR devuelve una cadena que especifica la versión del runtime que está cargada actualmente en el proceso. La cadena devuelta adopta el mismo formato como cadenas que se pasan al [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), por ejemplo, "v1.0.1216". Si el tiempo de ejecución aún no se han cargado en el proceso, la función devuelve la información de directorio adecuado para la versión más reciente del runtime instalada en el equipo.  
  
 `cchBuffer`  
 El número de caracteres (`WCHAR`s) que se pueden guardar en `pbuffer`.  
  
 `dwLength`  
 Un puntero al número de caracteres devueltos realmente en `pbuffer`. Si `pbuffer` es un puntero nulo, el tiempo de ejecución devuelve E_POINTER. Si el número de caracteres es mayor, a continuación, la longitud de `pbuffer` , el tiempo de ejecución devuelve ERROR_INSUFFICIENT_BUFFER.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
