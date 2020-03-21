---
title: LoadStringRC (Función)
ms.date: 03/30/2017
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
ms.openlocfilehash: 56ae7b7cf3b577bfe41ebd0bdd98e0da68047b44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176245"
---
# <a name="loadstringrc-function"></a>LoadStringRC (Función)
Traduce un valor HRESULT en un mensaje de error mediante la referencia cultural predeterminada del subproceso actual.  
  
 Esta función ha quedado en desuso en .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `iResourceID`  
 [in] HRESULT.  
  
 `szBuffer`  
 [fuera] Un búfer que contiene el mensaje de error al completarse correctamente.  
  
 `iMax`  
 [en] El tamaño del búfer de mensajes de error.  
  
 `bQuiet`  
 [en] Ignorado.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error estándar del modelo de objetos componentes (COM), tal como se define en WinError.h, además de los siguientes valores.  
  
|Código de retorno|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`szBuffer`es nulo `iMax` o es cero (0).|  
  
## <a name="remarks"></a>Observaciones  
 Si el método no se `szBuffer` completa correctamente, contiene una cadena vacía.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MScorEE.h  
  
 **Biblioteca:** MSCorEE.dll y Mscorwks.dll. Use MSCorEE.dll en lugar de Mscorwks.dll para asegurarse de que tiene como destino la versión correcta de .NET Framework.  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [LoadStringRCEx (Función)](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
