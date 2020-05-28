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
ms.openlocfilehash: a11b7d5939c4c20504b1ff3dfb4613f85bca0db4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007980"
---
# <a name="cor_native_link-structure"></a>COR_NATIVE_LINK (Estructura)
Contiene información que se utiliza para vincular el código nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`m_linkType`|Tipo que se va a vincular en código nativo. Este valor es uno de los valores de [cornativelinktype (](cornativelinktype-enumeration.md) .|  
|`m_flags`|Marcas usadas por el enlazador al vincular código nativo. Este valor es uno de los valores de [CorNativeLinkFlags (](cornativelinkflags-enumeration.md) .|  
|`m_entryPoint`|Símbolo (token) de metadatos de MemberRef que representa el punto de entrada. El formato es `lib:entrypoint`.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de metadatos](metadata-structures.md)
- [CorNativeLinkType (Enumeración)](cornativelinktype-enumeration.md)
- [CorNativeLinkFlags (Enumeración)](cornativelinkflags-enumeration.md)
