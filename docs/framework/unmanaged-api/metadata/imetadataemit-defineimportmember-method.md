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
ms.openlocfilehash: a7449ffc8a8ccf2db62ab3cff2f9cfaffd0c72a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175868"
---
# <a name="imetadataemitdefineimportmember-method"></a>IMetaDataEmit::DefineImportMember (Método)
Crea una referencia al miembro especificado de un tipo o módulo que se define fuera del ámbito actual y define un token para esa referencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 [en] Una interfaz [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) que representa el ensamblado desde el que se importa el miembro de destino.  
  
 `pbHashValue`  
 [en] Matriz que contiene el hash del `pAssemImport`ensamblado especificado por .  
  
 `cbHashValue`  
 [in] Número de bytes en la matriz `pbHashValue`.  
  
 `pImport`  
 [en] Una interfaz [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) que representa el ámbito de metadatos desde el que se importa el miembro de destino.  
  
 `mbMember`  
 [en] El token de metadatos que especifica el miembro de destino. El token puede `mdMethodDef` ser un token `mdProperty` (para un método `mdFieldDef` miembro), (para una propiedad miembro) o (para un campo miembro).  
  
 `pAssemEmit`  
 [en] Una [interfaz IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) que representa el ensamblado en el que se importa el miembro de destino.  
  
 `tkParent`  
 [en] El `mdTypeRef` `mdModuleRef` token o para el tipo o módulo, respectivamente, que posee el miembro de destino.  
  
 `pmr`  
 [fuera] El `mdMemberRef` token que se define en el ámbito actual para la referencia de miembro.  
  
## <a name="remarks"></a>Observaciones  
 El `DefineImportMember` método busca el miembro, `mbMember`especificado por , que se `pImport`define en otro ámbito, especificado por , y recupera sus propiedades. Usa esta información para llamar a la [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) método en el ámbito actual para crear la referencia de miembro.  
  
 Por lo general, `DefineImportMember` antes de usar el método, debe crear, en el ámbito actual, una referencia de tipo o una referencia de módulo para la clase primaria, la interfaz o el módulo del miembro de destino. A continuación, el token de `tkParent` metadatos para esta referencia se pasa en el argumento. No es necesario crear una referencia al elemento primario del miembro de destino si el compilador o vinculador la resolverá más adelante. Resumiendo:  
  
- Si el miembro de destino es un campo o método, utilice el [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) o el [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) método para crear una referencia de tipo, en el ámbito actual, para la clase primaria del miembro o la interfaz primaria.  
  
- Si el miembro de destino es una variable global o una función global (es decir, no un miembro de una clase o interfaz), utilice el [método IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) para crear una referencia de módulo, en el ámbito actual, para el módulo primario del miembro.  
  
- Si el compilador o vinculador resolverá el elemento primario `mdTokenNil` del `tkParent`miembro de destino más adelante, pase . El único escenario en el que esto se aplica es cuando una función global o variable global se está importando desde un archivo .obj que, en última instancia, se vinculará al módulo actual y los metadatos se fusionarán.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
