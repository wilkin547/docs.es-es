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
ms.openlocfilehash: 1aabfad14ee2eb35916bbf115631602276cd1fc3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109892"
---
# <a name="gethistoryfiledirectory-function"></a>GetHistoryFileDirectory (Función)
Recupera la ruta de acceso del directorio del historial de la aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wzDir`  
 enuncia Un búfer que contiene la ruta de acceso al directorio del historial de la aplicación.  
  
 `pdwSize`  
 [in, out] Longitud del búfer.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los códigos de error COM estándar, tal y como se define en el archivo WinError. h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`wzDir` o `pdwSize` es null, o la cadena de versión es incorrecta.|  
  
## <a name="remarks"></a>Comentarios  
 Si se completa correctamente, el argumento `pdwSize` se establece en la longitud de la cadena de ruta de acceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Biblioteca:** Fusion. dll y mscorwks. dll. Use Fusion. dll en lugar de mscorwks. dll para asegurarse de que tiene como destino la versión correcta del .NET Framework.  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CreateHistoryReader (Función)](createhistoryreader-function.md)
- [NukeDownloadedCache (Función)](nukedownloadedcache-function.md)
- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
