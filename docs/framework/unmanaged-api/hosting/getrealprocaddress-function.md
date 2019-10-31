---
title: GetRealProcAddress (Función)
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
ms.openlocfilehash: 9dffc3d197b05bb71443aa60c101260daabadadd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136402"
---
# <a name="getrealprocaddress-function"></a>GetRealProcAddress (Función)
Obtiene la dirección de la función especificada que se exporta de la última versión instalada del Common Language Runtime (CLR).  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwszProcName`  
 de Nombre de la función.  
  
 `ppv`  
 enuncia La ubicación que recibe un puntero a la dirección de la función.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los siguientes valores definidos en CorError. h.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`ppv` no es válido.|  
|CLR_E_SHIM_RUNTIMEEXPORT|La función no se exporta desde el tiempo de ejecución.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
