---
title: ILCodeKind (Enumeración)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ILCodeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type:
- apiref
ms.openlocfilehash: 7e9cf760ec609786804a05177349ee2eacd79eaf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692246"
---
# <a name="ilcodekind-enumeration"></a>ILCodeKind (Enumeración)

[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Proporciona valores que especifican si el depurador puede acceder a las variables locales o al código agregados en la instrumentación ReJIT del generador de perfiles.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a>Miembros  
  
|Nombre del miembro|Descripción|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|El depurador no tiene acceso a la información de la instrumentación ReJIT.|  
|`ILCODE_REJIT_IL`|El depurador tiene acceso a la información de la instrumentación ReJIT.|  
  
## <a name="remarks"></a>Comentarios  

 Un miembro de la `ILCodeKind` enumeración se puede pasar a los métodos [Enumeratelocalvariablesex (](icordebugilframe4-enumeratelocalvariablesex-method.md) y [getlocalvariableex (](icordebugilframe4-getlocalvariableex-method.md) para determinar si el depurador puede tener acceso a las variables agregadas en la instrumentación ReJIT del generador de perfiles y al método [getcodeex (](icordebugilframe4-getcodeex-method.md) para determinar si el depurador puede tener acceso al Il instrumentado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones de depuración](debugging-enumerations.md)
- [ICorDebugILFrame4 (Interfaz)](icordebugilframe4-interface.md)
- [ReJIT: Guía de How-To](/archive/blogs/davbr/rejit-a-how-to-guide)
