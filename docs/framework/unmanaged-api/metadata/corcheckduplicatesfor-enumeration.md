---
title: "CorCheckDuplicatesFor (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorCheckDuplicatesFor
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCheckDuplicatesFor
helpviewer_keywords: CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d9bd0409f22e6ca47a7bc97bec634381158167da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corcheckduplicatesfor-enumeration"></a>CorCheckDuplicatesFor (Enumeración)
Especifica los tokens de metadatos que se va a comprobar si existen duplicados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|`MDDupAll`|Compruebe todos los tokens de metadatos para los duplicados.|  
|`MDDupENC`|No usado.|  
|`MDNoDupChecks`|No proteja los tokens de metadatos para los duplicados.|  
|`MDDupTypeDef`|Compruebe si existen duplicados de `mdTypeDef` símbolos (tokens).|  
|`MDDupInterfaceImpl`|Compruebe si existen duplicados de `mdInterfaceImpl` símbolos (tokens).|  
|`MDDupMethodDef`|Compruebe si existen duplicados de `mdMethodDef` símbolos (tokens).|  
|`MDDupTypeRef`|Compruebe si existen duplicados de `mdTypeRef` símbolos (tokens).|  
|`MDDupMemberRef`|Compruebe si existen duplicados de `mdMemberRef` símbolos (tokens).|  
|`MDDupCustomAttribute`|Compruebe si existen duplicados de `mdCustomAttribute` símbolos (tokens).|  
|`MDDupParamDef`|Compruebe si existen duplicados de `mdParamDef` símbolos (tokens).|  
|`MDDupPermission`|Compruebe si existen duplicados de `mdPermission` símbolos (tokens).|  
|`MDDupProperty`|Compruebe si existen duplicados de `mdProperty` símbolos (tokens).|  
|`MDDupEvent`|Compruebe si existen duplicados de `mdEvent` símbolos (tokens).|  
|`MDDupFieldDef`|Compruebe si existen duplicados de `mdFieldDef` símbolos (tokens).|  
|`MDDupSignature`|Compruebe si existen duplicados de `mdSignature` símbolos (tokens).|  
|`MDDupModuleRef`|Compruebe si existen duplicados de `mdModuleRef` símbolos (tokens).|  
|`MDDupTypeSpec`|Compruebe si existen duplicados de `mdTypeSpec` símbolos (tokens).|  
|`MDDupImplMap`|Compruebe si existen duplicados de `mdImplMap` símbolos (tokens).|  
|`MDDupAssemblyRef`|Compruebe si existen duplicados de `mdAssemblyRef` símbolos (tokens).|  
|`MDDupFile`|Compruebe si existen duplicados de `mdFile` símbolos (tokens).|  
|`MDDupExportedType`|Compruebe si existen duplicados de `mdExportedType` símbolos (tokens).|  
|`MDDupManifestResource`|Compruebe si existen duplicados de `mdManifestResource` símbolos (tokens).|  
|`MDDupGenericParam`|Compruebe si existen duplicados de `mdGenericParam` símbolos (tokens).|  
|`MDDupMethodSpec`|Compruebe si existen duplicados de `mdMethodSpec` símbolos (tokens).|  
|`MDDupGenericParamConstraint`|Compruebe si existen duplicados de `mdGenericParamConstraint` símbolos (tokens).|  
|`MDDupAssembly`|Compruebe si existen duplicados de `mdAssembly` símbolos (tokens).|  
|`MDDupDefault`|Compruebe si existen duplicados de `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, y `mdMethodSpec` símbolos (tokens).|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
