---
description: 'Más información acerca de: estructura Bucketparameters ('
title: BucketParameters (Estructura)
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
ms.openlocfilehash: e2d701caa0e2374cb6b44d5fb5537f2ecc7e34fd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799972"
---
# <a name="bucketparameters-structure"></a>BucketParameters (Estructura)

Almacena el nombre de tipo de un evento y los parámetros de la excepción actual que está asociada al evento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`fInited`|`true`, si el resto de esta estructura es válido; en caso contrario, `false` .|  
|`pszEventTypeName`|Nombre del tipo de evento.|  
|`pszParams`|Matriz de cadenas, cada una de las cuales especifica un parámetro para la excepción actual asociada al evento.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. idl  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de hospedaje](hosting-structures.md)
