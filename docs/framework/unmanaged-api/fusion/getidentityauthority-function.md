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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eae17c2dbccb4296d7542c60a30b341f1ad67f88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429571"
---
# <a name="getidentityauthority-function"></a>GetIdentityAuthority (Función)
Obtiene un puntero a un [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instancia que administra las claves para los objetos de código.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppIIdentityAuthority`  
 [out] El valor devuelto `IIdentityAuthority` puntero.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Isolation.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IIdentityAuthority (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
