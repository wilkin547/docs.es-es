---
title: "LoadStringRC (Función)"
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
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2fd42a576e1315ea029f98b94d8dc84d2b92b5e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="loadstringrc-function"></a>LoadStringRC (Función)
Convierte un valor HRESULT en un mensaje de error mediante el uso de la referencia cultural predeterminada del subproceso actual.  
  
 Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `iResourceID`  
 [in] Un valor de HRESULT.  
  
 `szBuffer`  
 [out] Un búfer que contiene el mensaje de error una vez completada correctamente.  
  
 `iMax`  
 [in] El tamaño del búfer de mensaje de error.  
  
 `bQuiet`  
 [in] Pasa por alto.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error estándar de modelo de objetos componentes (COM), como se define en WinError.h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`szBuffer`es null o `iMax` es cero (0).|  
  
## <a name="remarks"></a>Comentarios  
 Si el método no se completa correctamente, `szBuffer` contiene una cadena vacía.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll y Mscorwks.dll. Use MSCorEE.dll en lugar de Mscorwks.dll para asegurarse de que la versión correcta de .NET Framework de destino.  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [LoadStringRCEx (Función)](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
