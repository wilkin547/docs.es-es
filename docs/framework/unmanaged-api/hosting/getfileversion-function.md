---
title: GetFileVersion (Función)
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
ms.openlocfilehash: 57b30824c7849127f48d4da61872945366e7141e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733248"
---
# <a name="getfileversion-function"></a>GetFileVersion (Función)

Obtiene la información de la versión de Common Language Runtime (CLR) del archivo especificado, utilizando el búfer especificado.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `szFilename`  
 de Ruta de acceso del archivo que se va a examinar.  
  
 `szBuffer`  
 [in, out] Búfer asignado para la información de versión que se devuelve.  
  
 `cchBuffer`  
 de Tamaño, en caracteres anchos, de `szBuffer` .  
  
 `dwLength`  
 enuncia Tamaño, en bytes, del devuelto `szBuffer` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
