---
title: IMetaDataEmit::DefineImportMember (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 81acda4d395563fc8e0000e38036d1aaa0f14471
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222697"
---
# <a name="imetadataemitdefineimportmember-method"></a>IMetaDataEmit::DefineImportMember (Método)
Crea una referencia al miembro especificado de un tipo o módulo que se define fuera del ámbito actual y define un token para esa referencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineImportMember (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,   
    [in]  mdToken                  mbMember,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [in]  mdToken                  tkParent,   
    [out] mdMemberRef              *pmr   
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pAssemImport`  
 [in] Un [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz que representa el ensamblado del que se importa el miembro de destino.  
  
 `pbHashValue`  
 [in] Una matriz que contiene el valor hash para el ensamblado especificado por `pAssemImport`.  
  
 `cbHashValue`  
 [in] Número de bytes en la matriz `pbHashValue`.  
  
 `pImport`  
 [in] Un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz que representa el ámbito de metadatos desde el que se importa el miembro de destino.  
  
 `mbMember`  
 [in] El token de metadatos que especifica al miembro de destino. El token puede ser un `mdMethodDef` (para un método de miembro), `mdProperty` (para una propiedad de miembro), o `mdFieldDef` (para un campo de miembro) token.  
  
 `pAssemEmit`  
 [in] Un [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interfaz que representa el ensamblado al que se importa el miembro de destino.  
  
 `tkParent`  
 [in] El `mdTypeRef` o `mdModuleRef` token para el tipo o módulo, respectivamente, que posee el miembro de destino.  
  
 `pmr`  
 [out] El `mdMemberRef` símbolo (token) que se define en el ámbito actual para la referencia de miembro.  
  
## <a name="remarks"></a>Comentarios  
 El `DefineImportMember` método busca el miembro, especificado por `mbMember`, que son definidos en otro ámbito, como se especifica por `pImport`y recupera sus propiedades. Usa esta información para llamar a la [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) método en el ámbito actual para crear la referencia de miembro.  
  
 Por lo general, antes de usar el `DefineImportMember` método, debe crear, en el ámbito actual, una referencia de tipo o una referencia de módulo para el módulo, interfaz o clase primaria del miembro de destino. El token de metadatos para esta referencia se pasa a continuación, en el `tkParent` argumento. No es necesario crear una referencia al elemento primario del miembro de destino si se resolverán más adelante mediante el compilador o vinculador. En resumen:  
  
-   Si el miembro de destino es un campo o método, use cualquiera el [DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) o [DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) método para crear una referencia de tipo, en el ámbito actual, para el interfaz primaria o clase primaria del miembro.  
  
-   Si el miembro de destino es una función global o variable global (es decir, no un miembro de una clase o interfaz), use el [DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) método para crear una referencia de módulo, en el ámbito actual, para el elemento primario del miembro módulo.  
  
-   Si el elemento primario del miembro de destino se resolverán más adelante mediante el compilador o vinculador, a continuación, pasar `mdTokenNil` en `tkParent`. El único escenario en el que esto se aplica es cuando una función o variable global se va a importar desde un archivo .obj que se vinculará en última instancia en el módulo actual y la combinación de metadatos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
