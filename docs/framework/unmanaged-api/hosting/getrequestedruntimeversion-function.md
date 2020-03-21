---
title: GetRequestedRuntimeVersion (Función)
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
ms.openlocfilehash: 6be0bc5d08f612dcb8ed7d256711e0c4367b9274
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178137"
---
# <a name="getrequestedruntimeversion-function"></a>GetRequestedRuntimeVersion (Función)
Obtiene el número de versión de Common Language Runtime (CLR) solicitado por la aplicación especificada. Si esa versión no está instalada, obtiene la versión más reciente que se instala antes de la versión solicitada.  
  
 Esta función ha quedado en desuso en .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pExe`  
 [en] El nombre de la aplicación.  
  
 `pVersion`  
 [fuera] Un búfer que contiene la cadena de número de versión una vez completado correctamente.  
  
 `cchBuffer`  
 [en] La longitud del búfer de versión.  
  
 `pdwLength`  
 [fuera] Un puntero a la longitud de la cadena de número de versión.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error estándar del modelo de objetos componentes (COM), tal como se define en WinError.h, además de los siguientes valores.  
  
|Código de retorno|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|ERROR_INSUFFICIENT_BUFFER|El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.|  
|E_POINTER|`pdwLength` es null.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MScorEE.h  
  
 **Biblioteca:** Mscoree.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [GetRequestedRuntimeInfo (Función)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [GetVersionFromProcess (Función)](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
