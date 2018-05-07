---
title: COR_NATIVE_LINK (Estructura)
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0d9b8a9a1014d98c51f1471f8203be07f7ff49c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cornativelink-structure"></a>COR_NATIVE_LINK (Estructura)
Contiene información que se utiliza para vincular el código nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`m_linkType`|El tipo esté vinculado en código nativo. Este valor es uno de los [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) valores.|  
|`m_flags`|Marcadores utilizados por el vinculador al vincular código nativo. Este valor es uno de los [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) valores.|  
|`m_entryPoint`|El token de metadatos de MemberRef que representa el punto de entrada. El formato es `lib:entrypoint`.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [CorNativeLinkType (enumeración)](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 [CorNativeLinkFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
