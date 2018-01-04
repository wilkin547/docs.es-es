---
title: "GetHistoryFileDirectory (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHistoryFileDirectory
api_location: fusion.dll
api_type: DLLExport
f1_keywords: GetHistoryFileDirectory
helpviewer_keywords: GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d0ec18a4f95d0d280a66b3b9d9200c560f5f187
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="gethistoryfiledirectory-function"></a>GetHistoryFileDirectory (Función)
Recupera la ruta de acceso del directorio de historial de la aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `wzDir`  
 [out] Un búfer para almacenar la ruta de acceso al directorio de historial de la aplicación.  
  
 `pdwSize`  
 [entrada, salida] La longitud del búfer.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error COM estándar, tal como se define en el archivo WinError.h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`wzDir`o `pdwSize` es nulo o la versión de cadena no es correcta.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando se finaliza correctamente, el `pdwSize` argumento se establece en la longitud de la cadena de ruta de acceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Biblioteca:** Fusion.dll y Mscorwks.dll. Use Fusion.dll en lugar de Mscorwks.dll para asegurarse de que la versión correcta de .NET Framework de destino.  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [CreateHistoryReader (Función)](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [NukeDownloadedCache (Función)](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
