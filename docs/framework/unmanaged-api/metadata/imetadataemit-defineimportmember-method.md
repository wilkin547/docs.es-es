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
ms.openlocfilehash: f9995fda70d1d5a3c19c30496de6c32f20015d47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449395"
---
# <a name="imetadataemitdefineimportmember-method"></a>IMetaDataEmit::DefineImportMember (Método)
Crea una referencia al miembro especificado de un tipo o módulo que se define fuera del ámbito actual y define un símbolo (token) para esa referencia.  
  
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
  
#### <a name="parameters"></a>Parámetros  
 `pAssemImport`  
 [in] Un [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz que representa el ensamblado desde el que se importa el miembro de destino.  
  
 `pbHashValue`  
 [in] Una matriz que contiene el valor hash para el ensamblado especificado por `pAssemImport`.  
  
 `cbHashValue`  
 [in] Número de bytes en la matriz `pbHashValue`.  
  
 `pImport`  
 [in] Un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz que representa el ámbito de metadatos desde el que se importa el miembro de destino.  
  
 `mbMember`  
 [in] El token de metadatos que especifica al miembro de destino. El token puede ser un `mdMethodDef` (para un método de miembro), `mdProperty` (para una propiedad de miembro), o `mdFieldDef` (para un campo de miembro) símbolo (token).  
  
 `pAssemEmit`  
 [in] Un [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interfaz que representa el ensamblado al que se importa el miembro de destino.  
  
 `tkParent`  
 [in] El `mdTypeRef` o `mdModuleRef` símbolo (token) para el tipo o módulo, respectivamente, que posee el miembro de destino.  
  
 `pmr`  
 [out] El `mdMemberRef` (token) que se define en el ámbito actual para la referencia de miembro.  
  
## <a name="remarks"></a>Comentarios  
 El `DefineImportMember` método busca el miembro, especificado por `mbMember`, que se define en otro ámbito, especificado por `pImport`y recupera sus propiedades. Esta información se utiliza para llamar a la [IMetaDataEmit:: DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) método en el ámbito actual que se va a crear la referencia de miembro.  
  
 Por lo general, antes de utilizar el `DefineImportMember` método, debe crear, en el ámbito actual, una referencia de tipo o la referencia de módulo para el módulo, interfaz o clase primaria del miembro de destino. El token de metadatos para esta referencia se pasa a continuación, en la `tkParent` argumento. No es necesario crear una referencia al elemento primario del miembro de destino si se resolverán más tarde mediante el compilador o el vinculador. En resumen:  
  
-   Si el miembro de destino es un campo o método, use la [IMetaDataEmit:: DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) o [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) método para crear una referencia de tipo, en el ámbito actual, para el interfaz primaria o clase primaria del miembro.  
  
-   Si el miembro de destino es una función global o variable global (es decir, no un miembro de una clase o interfaz), use la [IMetaDataEmit:: DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) método para crear una referencia al módulo, en el ámbito actual, para el elemento primario del miembro módulo.  
  
-   Si se puede resolver el elemento primario del miembro de destino más adelante mediante el compilador o el vinculador, a continuación, pasar `mdTokenNil` en `tkParent`. El único escenario en el que se aplica esto es cuando una función global o variable global se va a importar desde un archivo .obj que se vinculará, en última instancia, en el módulo actual y la combinación de metadatos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
