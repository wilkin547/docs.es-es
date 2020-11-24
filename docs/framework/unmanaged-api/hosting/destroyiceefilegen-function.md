---
title: DestroyICeeFileGen (Función)
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
ms.openlocfilehash: 495d84470c559df13ea64b63dd00582f4335d4e3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673201"
---
# <a name="destroyiceefilegen-function"></a>DestroyICeeFileGen (Función)

Destruye un objeto [ICeeFileGen](iceefilegen-class.md) .  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ceeFileGen`  
 de `ICeeFileGen` Objeto que se va a destruir.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los códigos de error COM estándar.  
  
## <a name="remarks"></a>Comentarios  

 `DestroyICeeFileGen` destruye el `ICeeFileGen` objeto creado por la función [CreateICeeFileGen (](createiceefilegen-function.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ICeeFileGen. h  
  
 **Biblioteca:** MSCorPE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
