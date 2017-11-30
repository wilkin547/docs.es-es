---
title: "CorTokenType (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorTokenType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorTokenType
helpviewer_keywords: CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1910321942ebac26d8c377f9d156cdf97bd34b62
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cortokentype-enumeration"></a>CorTokenType (Enumeración)
Indica el tipo de un token de metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`mdtModule`|Un `mdModule` símbolo (token).|  
|`mdtTypeRef`|Un `mdTypeRef` símbolo (token).|  
|`mdtTypeDef`|Un `mdTypeDef` símbolo (token).|  
|`mdtFieldDef`|Un `mdFieldDef` símbolo (token).|  
|`mdtMethodDef`|Un `mdMethodDef` símbolo (token).|  
|`mdtParamDef`|Un `mdParamDef` símbolo (token).|  
|`mdtInterfaceImpl`|Un `mdInterfaceImpl` símbolo (token).|  
|`mdtMemberRef`|Un `mdMemberRef` símbolo (token).|  
|`mdtCustomAttribute`|Un `mdCustomAttribute` símbolo (token).|  
|`mdtPermission`|Un `mdPermission` símbolo (token).|  
|`mdtSignature`|Un `mdSignature` símbolo (token).|  
|`mdtEvent`|Un `mdEvent` símbolo (token).|  
|`mdtProperty`|Un `mdProperty` símbolo (token).|  
|`mdtModuleRef`|Un `mdModuleRef` símbolo (token).|  
|`mdtTypeSpec`|Un `mdTypeSpec` símbolo (token).|  
|`mdtAssembly`|Un `mdAssembly` símbolo (token).|  
|`mdtAssemblyRef`|Un `mdAssemblyRef` símbolo (token).|  
|`mdtFile`|Un `mdFile` símbolo (token).|  
|`mdtExportedType`|Un `mdExportedType` símbolo (token).|  
|`mdtManifestResource`|Un `mdManifestResource` símbolo (token).|  
|`mdtGenericParam`|Un `mdGenericParam` símbolo (token).|  
|`mdtMethodSpec`|Un `mdMethodSpec` símbolo (token).|  
|`mdtGenericParamConstraint`|Un `mdGenericParamConstraint` símbolo (token).|  
|`mdtString`|Un `mdString` símbolo (token).|  
|`mdtName`|Un `mdName` símbolo (token).|  
|`mdtBaseType`|No usado.|  
  
## <a name="remarks"></a>Comentarios  
 Cada valor es igual que el valor del byte superior en el token de metadatos correspondiente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
