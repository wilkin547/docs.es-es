---
title: GetHistoryFileDirectory (Función)
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b60dde31707175a27d2dc6c50484d6089adaeaa6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229633"
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
  
## <a name="parameters"></a>Parámetros  
 `wzDir`  
 [out] Un búfer para almacenar la ruta de acceso al directorio de historial de la aplicación.  
  
 `pdwSize`  
 [in, out] La longitud del búfer.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error COM estándar, tal como se define en el archivo WinError.h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`wzDir` o `pdwSize` es null, o la versión de cadena no es correcta.|  
  
## <a name="remarks"></a>Comentarios  
 Se completa correctamente, el `pdwSize` argumento está establecido en la longitud de la cadena de ruta de acceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Fusion.h  
  
 **Biblioteca:** El archivo Fusion.dll y Mscorwks.dll. Use el archivo Fusion.dll en lugar de Mscorwks.dll para asegurarse de que tener como destino la versión correcta de .NET Framework.  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CreateHistoryReader (Función)](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [NukeDownloadedCache (Función)](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)
- [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
