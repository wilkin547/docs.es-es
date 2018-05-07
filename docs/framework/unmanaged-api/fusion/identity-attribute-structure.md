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
ms.openlocfilehash: f716ff35ae0cd3d2a53c55756b8957e54fa355c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="identityattribute-structure"></a>IDENTITY_ATTRIBUTE (Estructura)
Contiene información de atributos de metadatos sobre un [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instancia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`pszNamespace`|Un puntero a una cadena de caracteres terminada en null que contiene el espacio de nombres del atributo está en.|  
|`pszName`|Un puntero a una cadena de caracteres terminada en null que contiene el nombre del atributo.|  
|`pszValue`|Un puntero a una cadena de caracteres terminada en null que contiene el valor del atributo.|  
  
## <a name="remarks"></a>Comentarios  
 El `IDENTITY_ATTRIBUTE` estructura contiene tres punteros a cadenas de caracteres terminada en null. Estas tres cadenas describen un atributo.  
  
 Una instancia de un `IDENTITY_ATTRIBUTE` estructura está asociada a una instancia de un [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) estructura. El `IDENTITY_ATTRIBUTE` estructura contiene las cadenas reales y las correspondientes `IDENTITY_ATTRIBUTE_BLOB` estructura enumera los desplazamientos a las tres cadenas enumeradas en la `IDENTITY_ATTRIBUTE` estructura.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Isolation.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IDefinitionIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 [IDENTITY_ATTRIBUTE_BLOB (estructura)](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)  
 [Estructuras de fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
