---
description: 'Más información acerca de: estructura de COR_NATIVE_LINK'
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
ms.openlocfilehash: 09c715af698a0614fd4a9a17679df6908a1497a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678580"
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`m_linkType`|Tipo que se va a vincular en código nativo. Este valor es uno de los valores de [cornativelinktype (](cornativelinktype-enumeration.md) .|  
|`m_flags`|Marcas usadas por el enlazador al vincular código nativo. Este valor es uno de los valores de [CorNativeLinkFlags (](cornativelinkflags-enumeration.md) .|  
|`m_entryPoint`|Símbolo (token) de metadatos de MemberRef que representa el punto de entrada. El formato es `lib:entrypoint`.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de metadatos](metadata-structures.md)
- [CorNativeLinkType (Enumeración)](cornativelinktype-enumeration.md)
- [CorNativeLinkFlags (Enumeración)](cornativelinkflags-enumeration.md)
