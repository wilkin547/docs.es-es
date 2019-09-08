---
title: IDENTITY_ATTRIBUTE (Estructura)
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0bcabb32d50b236d42a555c073b50ba3a234dde
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796490"
---
# <a name="identity_attribute-structure"></a>IDENTITY_ATTRIBUTE (Estructura)
Contiene información de atributos de metadatos sobre una instancia de [IDefinitionIdentity](idefinitionidentity-interface.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`pszNamespace`|Un puntero a una cadena de caracteres terminada en null que contiene el espacio de nombres en el que se encuentra el atributo.|  
|`pszName`|Puntero a una cadena de caracteres terminada en null que contiene el nombre del atributo.|  
|`pszValue`|Puntero a una cadena de caracteres terminada en null que contiene el valor del atributo.|  
  
## <a name="remarks"></a>Comentarios  
 La `IDENTITY_ATTRIBUTE` estructura contiene tres punteros a cadenas de caracteres terminadas en NULL. Estas tres cadenas describen un atributo.  
  
 Una instancia de una `IDENTITY_ATTRIBUTE` estructura está asociada a una instancia de una estructura [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) . La `IDENTITY_ATTRIBUTE` estructura contiene las cadenas reales y la estructura correspondiente `IDENTITY_ATTRIBUTE_BLOB` muestra los desplazamientos a las tres cadenas enumeradas en `IDENTITY_ATTRIBUTE` la estructura.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IDefinitionIdentity (interfaz)](idefinitionidentity-interface.md)
- [IDENTITY_ATTRIBUTE_BLOB (estructura)](identity-attribute-blob-structure.md)
- [Estructuras de fusión](fusion-structures.md)
