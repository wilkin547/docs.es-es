---
title: MALLOC_TYPE (enumeración)
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
ms.openlocfilehash: 630fe4e79b369bfdefc19be72780f1893090895e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008461"
---
# <a name="malloc_type-enumeration"></a>MALLOC_TYPE (enumeración)
Contiene valores que especifican las características de la memoria que se va a asignar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|La memoria asignada puede contener un archivo ejecutable.|  
|`MALLOC_THREADSAFE`|La memoria asignada es segura para subprocesos. Es decir, se puede tener acceso a la memoria por parte de varios subprocesos sin ninguna sincronización.<br /><br /> Si no se establece esta marca, se deben serializar las llamadas en el objeto.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para hosts](hosting-enumerations.md)
