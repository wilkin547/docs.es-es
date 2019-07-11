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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9047bf973224cdbc1f67463ef70f15f81089f827
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768459"
---
# <a name="loadstringrc-function"></a>LoadStringRC (Función)
Convierte un valor HRESULT en un mensaje de error mediante el uso de la referencia cultural predeterminada del subproceso actual.  
  
 Esta función está desusada en .NET Framework 4.  
  
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
 [in] Un HRESULT.  
  
 `szBuffer`  
 [out] Un búfer que contiene el mensaje de error tras completarse correctamente.  
  
 `iMax`  
 [in] El tamaño del búfer de mensaje de error.  
  
 `bQuiet`  
 [in] Pasa por alto.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error de modelo de objetos componentes (COM) estándar, tal como se define en WinError.h, además de los valores siguientes.  
  
|Código devuelto|DESCRIPCIÓN|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`szBuffer` es null o `iMax` es cero (0).|  
  
## <a name="remarks"></a>Comentarios  
 Si el método no se completa correctamente, `szBuffer` contiene una cadena vacía.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll y Mscorwks.dll. Use MSCorEE.dll en lugar de Mscorwks.dll para asegurarse de que tener como destino la versión correcta de .NET Framework.  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [LoadStringRCEx (Función)](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
