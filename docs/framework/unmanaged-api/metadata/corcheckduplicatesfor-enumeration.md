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
ms.openlocfilehash: 6b551743227dc1c6069796038782a515e6dbe8c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443778"
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
|`MDDupENC`|No usado.|  
|`MDNoDupChecks`|No Compruebe los tokens de metadatos en busca de duplicados.|  
|`MDDupTypeDef`|Compruebe si hay duplicados de tokens de `mdTypeDef`.|  
|`MDDupInterfaceImpl`|Compruebe si hay duplicados de tokens de `mdInterfaceImpl`.|  
|`MDDupMethodDef`|Compruebe si hay duplicados de tokens de `mdMethodDef`.|  
|`MDDupTypeRef`|Compruebe si hay duplicados de tokens de `mdTypeRef`.|  
|`MDDupMemberRef`|Compruebe si hay duplicados de tokens de `mdMemberRef`.|  
|`MDDupCustomAttribute`|Compruebe si hay duplicados de tokens de `mdCustomAttribute`.|  
|`MDDupParamDef`|Compruebe si hay duplicados de tokens de `mdParamDef`.|  
|`MDDupPermission`|Compruebe si hay duplicados de tokens de `mdPermission`.|  
|`MDDupProperty`|Compruebe si hay duplicados de tokens de `mdProperty`.|  
|`MDDupEvent`|Compruebe si hay duplicados de tokens de `mdEvent`.|  
|`MDDupFieldDef`|Compruebe si hay duplicados de tokens de `mdFieldDef`.|  
|`MDDupSignature`|Compruebe si hay duplicados de tokens de `mdSignature`.|  
|`MDDupModuleRef`|Compruebe si hay duplicados de tokens de `mdModuleRef`.|  
|`MDDupTypeSpec`|Compruebe si hay duplicados de tokens de `mdTypeSpec`.|  
|`MDDupImplMap`|Compruebe si hay duplicados de tokens de `mdImplMap`.|  
|`MDDupAssemblyRef`|Compruebe si hay duplicados de tokens de `mdAssemblyRef`.|  
|`MDDupFile`|Compruebe si hay duplicados de tokens de `mdFile`.|  
|`MDDupExportedType`|Compruebe si hay duplicados de tokens de `mdExportedType`.|  
|`MDDupManifestResource`|Compruebe si hay duplicados de tokens de `mdManifestResource`.|  
|`MDDupGenericParam`|Compruebe si hay duplicados de tokens de `mdGenericParam`.|  
|`MDDupMethodSpec`|Compruebe si hay duplicados de tokens de `mdMethodSpec`.|  
|`MDDupGenericParamConstraint`|Compruebe si hay duplicados de tokens de `mdGenericParamConstraint`.|  
|`MDDupAssembly`|Compruebe si hay duplicados de tokens de `mdAssembly`.|  
|`MDDupDefault`|Compruebe si hay duplicados de `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`y `mdMethodSpec` tokens.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
