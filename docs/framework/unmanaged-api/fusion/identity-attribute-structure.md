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
ms.openlocfilehash: 8b7edf1cc642228c4a79c855b51727264f31741c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107981"
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
  
|Miembro|Descripción|  
|------------|-----------------|  
|`pszNamespace`|Un puntero a una cadena de caracteres terminada en null que contiene el espacio de nombres en el que se encuentra el atributo.|  
|`pszName`|Puntero a una cadena de caracteres terminada en null que contiene el nombre del atributo.|  
|`pszValue`|Puntero a una cadena de caracteres terminada en null que contiene el valor del atributo.|  
  
## <a name="remarks"></a>Comentarios  
 La estructura `IDENTITY_ATTRIBUTE` contiene tres punteros a cadenas de caracteres terminadas en NULL. Estas tres cadenas describen un atributo.  
  
 Una instancia de una estructura de `IDENTITY_ATTRIBUTE` está asociada a una instancia de una estructura [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) . La estructura `IDENTITY_ATTRIBUTE` contiene las cadenas reales y la estructura `IDENTITY_ATTRIBUTE_BLOB` correspondiente muestra los desplazamientos a las tres cadenas enumeradas en la estructura `IDENTITY_ATTRIBUTE`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IDefinitionIdentity (interfaz)](idefinitionidentity-interface.md)
- [IDENTITY_ATTRIBUTE_BLOB (estructura)](identity-attribute-blob-structure.md)
- [Estructuras de fusión](fusion-structures.md)
