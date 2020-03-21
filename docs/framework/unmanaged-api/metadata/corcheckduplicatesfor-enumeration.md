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
ms.openlocfilehash: 04dc12ab4d7d178ebf1575a3260f9f4981972782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176193"
---
# <a name="corcheckduplicatesfor-enumeration"></a>CorCheckDuplicatesFor (Enumeración)
Especifica los tokens de metadatos que se comprobarán en busca de duplicados.  
  
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
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`MDDupAll`|Compruebe todos los tokens de metadatos en busca de duplicados.|  
|`MDDupENC`|No se usa.|  
|`MDNoDupChecks`|No compruebe los tokens de metadatos en busca de duplicados.|  
|`MDDupTypeDef`|Compruebe si hay `mdTypeDef` duplicados de tokens.|  
|`MDDupInterfaceImpl`|Compruebe si hay `mdInterfaceImpl` duplicados de tokens.|  
|`MDDupMethodDef`|Compruebe si hay `mdMethodDef` duplicados de tokens.|  
|`MDDupTypeRef`|Compruebe si hay `mdTypeRef` duplicados de tokens.|  
|`MDDupMemberRef`|Compruebe si hay `mdMemberRef` duplicados de tokens.|  
|`MDDupCustomAttribute`|Compruebe si hay `mdCustomAttribute` duplicados de tokens.|  
|`MDDupParamDef`|Compruebe si hay `mdParamDef` duplicados de tokens.|  
|`MDDupPermission`|Compruebe si hay `mdPermission` duplicados de tokens.|  
|`MDDupProperty`|Compruebe si hay `mdProperty` duplicados de tokens.|  
|`MDDupEvent`|Compruebe si hay `mdEvent` duplicados de tokens.|  
|`MDDupFieldDef`|Compruebe si hay `mdFieldDef` duplicados de tokens.|  
|`MDDupSignature`|Compruebe si hay `mdSignature` duplicados de tokens.|  
|`MDDupModuleRef`|Compruebe si hay `mdModuleRef` duplicados de tokens.|  
|`MDDupTypeSpec`|Compruebe si hay `mdTypeSpec` duplicados de tokens.|  
|`MDDupImplMap`|Compruebe si hay `mdImplMap` duplicados de tokens.|  
|`MDDupAssemblyRef`|Compruebe si hay `mdAssemblyRef` duplicados de tokens.|  
|`MDDupFile`|Compruebe si hay `mdFile` duplicados de tokens.|  
|`MDDupExportedType`|Compruebe si hay `mdExportedType` duplicados de tokens.|  
|`MDDupManifestResource`|Compruebe si hay `mdManifestResource` duplicados de tokens.|  
|`MDDupGenericParam`|Compruebe si hay `mdGenericParam` duplicados de tokens.|  
|`MDDupMethodSpec`|Compruebe si hay `mdMethodSpec` duplicados de tokens.|  
|`MDDupGenericParamConstraint`|Compruebe si hay `mdGenericParamConstraint` duplicados de tokens.|  
|`MDDupAssembly`|Compruebe si hay `mdAssembly` duplicados de tokens.|  
|`MDDupDefault`|Compruebe si hay `mdMemberRef` `mdTypeRef`duplicados `mdTypeSpec`de `mdMethodSpec` , , `mdSignature`, y tokens.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
