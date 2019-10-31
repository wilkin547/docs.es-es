---
title: CreateICeeFileGen (Función)
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: de27851b4afc3eccad46531848c68723bff346d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136832"
---
# <a name="createiceefilegen-function"></a>CreateICeeFileGen (Función)
Crea un objeto [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) .  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ceeFileGen`  
 enuncia Puntero a la dirección de un nuevo objeto de `ICeeFileGen`.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los códigos de error COM estándar.  
  
## <a name="remarks"></a>Comentarios  
 El objeto `ICeeFileGen` se usa para crear archivos ejecutables portables (PE) de Common Language Runtime (CLR).  
  
 Llame a la función [DestroyICeeFileGen (](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) para destruir el objeto `ICeeFileGen` cuando termine.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ICeeFileGen. h  
  
 **Biblioteca:** MSCorPE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
