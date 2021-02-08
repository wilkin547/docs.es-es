---
description: 'Más información acerca de: GetRequestedRuntimeVersion ((función)'
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
ms.openlocfilehash: 836cc4b875ddc427c6779950f5b68d2df8b6ef75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785281"
---
# <a name="getrequestedruntimeversion-function"></a>GetRequestedRuntimeVersion (Función)

Obtiene el número de versión del Common Language Runtime (CLR) solicitado por la aplicación especificada. Si esa versión no está instalada, obtiene la versión más reciente instalada antes de la versión solicitada.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
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
 de El nombre de la aplicación.  
  
 `pVersion`  
 enuncia Un búfer que contiene la cadena del número de versión cuando se completa correctamente.  
  
 `cchBuffer`  
 de Longitud del búfer de versión.  
  
 `pdwLength`  
 enuncia Puntero a la longitud de la cadena del número de versión.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|ERROR_INSUFFICIENT_BUFFER|El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.|  
|E_POINTER|`pdwLength` es null.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetRequestedRuntimeInfo (Función)](getrequestedruntimeinfo-function.md)
- [GetVersionFromProcess (Función)](getversionfromprocess-function.md)
- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
