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
ms.openlocfilehash: a300c2679ef11a84edb2ab89c8dea96e445c9ee3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177980"
---
# <a name="loadstringrcex-function"></a>LoadStringRCEx (Función)
Traduce un valor HRESULT a un mensaje de error adecuado para la referencia cultural especificada.  
  
 Esta función ha quedado en desuso en .NET Framework 4.  
  
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
 [en] Identificador de referencia cultural. Pase -1 `lcid` para usar la referencia cultural predeterminada.  
  
 `iResourceID`  
 [in] HRESULT.  
  
 `szBuffer`  
 [fuera] Un búfer que contiene el mensaje de error al completarse correctamente.  
  
 `iMax`  
 [en] El tamaño del búfer de mensajes de error.  
  
 `bQuiet`  
 [en] Ignorado.  
  
 `pcwchUsed`  
 [fuera] Un puntero a la longitud del mensaje de error.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error COM estándar, tal como se define en WinError.h, además de los siguientes valores.  
  
|Código de retorno|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`szBuffer`es nulo, `iMax` o es cero (0).|  
  
## <a name="remarks"></a>Observaciones  
 Si el método no se `szBuffer` completa correctamente, contiene una cadena vacía.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MScorEE.h  
  
 **Biblioteca:** Mscoree.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [LoadStringRC (Función)](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
