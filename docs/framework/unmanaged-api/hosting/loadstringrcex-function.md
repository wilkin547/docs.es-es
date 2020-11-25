---
title: LoadStringRCEx (Función)
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
ms.openlocfilehash: 1aa5c9f5dd7dd63e69c2eed1f6dd8ad6f007f01f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727541"
---
# <a name="loadstringrcex-function"></a>LoadStringRCEx (Función)

Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `lcid`  
 de Identificador de referencia cultural. Pass-1 para `lcid` para utilizar la referencia cultural predeterminada.  
  
 `iResourceID`  
 [in] HRESULT.  
  
 `szBuffer`  
 enuncia Un búfer que contiene el mensaje de error tras una finalización correcta.  
  
 `iMax`  
 de Tamaño del búfer del mensaje de error.  
  
 `bQuiet`  
 de Tendrán.  
  
 `pcwchUsed`  
 enuncia Puntero a la longitud del mensaje de error.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`szBuffer` es null, o `iMax` es cero (0).|  
  
## <a name="remarks"></a>Comentarios  

 Si el método no se completa correctamente, `szBuffer` contiene una cadena vacía.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [LoadStringRC (Función)](loadstringrc-function.md)
- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
