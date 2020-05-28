---
title: CorCheckDuplicatesFor (Enumeración)
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
ms.openlocfilehash: 2985c419b25b8bf76df8fee0f0f37ba9ebee3df7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007911"
---
# <a name="corcheckduplicatesfor-enumeration"></a>CorCheckDuplicatesFor (Enumeración)
Especifica los tokens de metadatos en los que se comprobarán los duplicados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`MDDupAll`|Compruebe todos los tokens de metadatos en busca de duplicados.|  
|`MDDupENC`|No se usa.|  
|`MDNoDupChecks`|No Compruebe los tokens de metadatos en busca de duplicados.|  
|`MDDupTypeDef`|Compruebe si hay duplicados de `mdTypeDef` tokens.|  
|`MDDupInterfaceImpl`|Compruebe si hay duplicados de `mdInterfaceImpl` tokens.|  
|`MDDupMethodDef`|Compruebe si hay duplicados de `mdMethodDef` tokens.|  
|`MDDupTypeRef`|Compruebe si hay duplicados de `mdTypeRef` tokens.|  
|`MDDupMemberRef`|Compruebe si hay duplicados de `mdMemberRef` tokens.|  
|`MDDupCustomAttribute`|Compruebe si hay duplicados de `mdCustomAttribute` tokens.|  
|`MDDupParamDef`|Compruebe si hay duplicados de `mdParamDef` tokens.|  
|`MDDupPermission`|Compruebe si hay duplicados de `mdPermission` tokens.|  
|`MDDupProperty`|Compruebe si hay duplicados de `mdProperty` tokens.|  
|`MDDupEvent`|Compruebe si hay duplicados de `mdEvent` tokens.|  
|`MDDupFieldDef`|Compruebe si hay duplicados de `mdFieldDef` tokens.|  
|`MDDupSignature`|Compruebe si hay duplicados de `mdSignature` tokens.|  
|`MDDupModuleRef`|Compruebe si hay duplicados de `mdModuleRef` tokens.|  
|`MDDupTypeSpec`|Compruebe si hay duplicados de `mdTypeSpec` tokens.|  
|`MDDupImplMap`|Compruebe si hay duplicados de `mdImplMap` tokens.|  
|`MDDupAssemblyRef`|Compruebe si hay duplicados de `mdAssemblyRef` tokens.|  
|`MDDupFile`|Compruebe si hay duplicados de `mdFile` tokens.|  
|`MDDupExportedType`|Compruebe si hay duplicados de `mdExportedType` tokens.|  
|`MDDupManifestResource`|Compruebe si hay duplicados de `mdManifestResource` tokens.|  
|`MDDupGenericParam`|Compruebe si hay duplicados de `mdGenericParam` tokens.|  
|`MDDupMethodSpec`|Compruebe si hay duplicados de `mdMethodSpec` tokens.|  
|`MDDupGenericParamConstraint`|Compruebe si hay duplicados de `mdGenericParamConstraint` tokens.|  
|`MDDupAssembly`|Compruebe si hay duplicados de `mdAssembly` tokens.|  
|`MDDupDefault`|Compruebe si hay duplicados de,,, `mdMemberRef` `mdTypeRef` `mdSignature` `mdTypeSpec` y `mdMethodSpec` tokens.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
