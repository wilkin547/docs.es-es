---
title: "NukeDownloadedCache (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: NukeDownloadedCache
helpviewer_keywords: NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5ff24cf46ab24fe94ab19cee04d9e32ed1a34b53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="nukedownloadedcache-function"></a>NukeDownloadedCache (Función)
Elimina la caché de descarga de common language runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error COM estándar, tal como se define en WinError.h.  
  
## <a name="remarks"></a>Comentarios  
 La caché de descarga CLR es el área donde se almacenan los ensamblados con nombre seguro que se descargan desde una dirección URL para una posible reutilización.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Biblioteca:** Fusion.dll y Mscorwks.dll. Use Fusion.dll en lugar de Mscorwks.dll para asegurarse de que la versión correcta de .NET Framework de destino.  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [CreateHistoryReader (función)](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [GetHistoryFileDirectory (función)](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [Funciones estáticas globales de fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
