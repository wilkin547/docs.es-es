---
title: "CreateHistoryReader (Función)"
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
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ab5e54735c360cb7bd2e681c04b0b1ae491bd716
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="createhistoryreader-function"></a>CreateHistoryReader (Función)
Crea un lector de historial para el archivo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `wzFilePath`  
 [in] La ruta de acceso de archivo.  
  
 `ppHistoryReader`  
 [out] Cuando se finaliza correctamente, contiene un puntero al lector de historial.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los códigos de error COM estándar definidos en WinError.h, además de los valores descritos en la tabla siguiente.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|Indica que el método se completó correctamente.|  
|E_INVALIDARG|Indica que `wzFilePath` o `ppHistoryReader` se establecen en una referencia nula.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Biblioteca:** Fusion.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
