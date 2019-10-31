---
title: GetIdentityAuthority (Función)
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
ms.openlocfilehash: acb80f3cc199d4d9f774cb3898335d26fe44b807
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127149"
---
# <a name="getidentityauthority-function"></a>GetIdentityAuthority (Función)
Obtiene un puntero a una instancia de [iidentityauthority (](iidentityauthority-interface.md) que administra las claves de los objetos de código.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppIIdentityAuthority`  
 enuncia Puntero `IIdentityAuthority` devuelto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IIdentityAuthority (interfaz)](iidentityauthority-interface.md)
- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
