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
ms.openlocfilehash: 2facc63023a20dd6aaac64d7d036324c31658bc8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501318"
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
 de Una interfaz [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) que representa el ensamblado desde el que se importa el miembro de destino.  
  
 `pbHashValue`  
 de Una matriz que contiene el hash para el ensamblado especificado por `pAssemImport` .  
  
 `cbHashValue`  
 [in] Número de bytes en la matriz `pbHashValue`.  
  
 `pImport`  
 de Interfaz [IMetaDataImport](imetadataimport-interface.md) que representa el ámbito de metadatos desde el que se importa el miembro de destino.  
  
 `mbMember`  
 de Token de metadatos que especifica el miembro de destino. El token puede ser un `mdMethodDef` (para un método de miembro), `mdProperty` (para una propiedad de miembro) o un `mdFieldDef` token (para un campo de miembro).  
  
 `pAssemEmit`  
 de Una interfaz [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) que representa el ensamblado en el que se importa el miembro de destino.  
  
 `tkParent`  
 de El `mdTypeRef` `mdModuleRef` token o para el tipo o módulo, respectivamente, que posee el miembro de destino.  
  
 `pmr`  
 enuncia El `mdMemberRef` token que se define en el ámbito actual para la referencia de miembro.  
  
## <a name="remarks"></a>Comentarios  
 El `DefineImportMember` método busca el miembro, especificado por `mbMember` , que se define en otro ámbito, especificado por `pImport` , y recupera sus propiedades. Usa esta información para llamar al método [IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md) en el ámbito actual para crear la referencia de miembro.  
  
 Normalmente, antes de usar el `DefineImportMember` método, debe crear, en el ámbito actual, una referencia de tipo o referencia de módulo para la clase primaria, la interfaz o el módulo del miembro de destino. A continuación, se pasa el token de metadatos para esta referencia en el `tkParent` argumento. No es necesario crear una referencia al elemento primario del miembro de destino si el compilador o el vinculador lo resolverán más adelante. En resumen:  
  
- Si el miembro de destino es un campo o un método, use el método [IMetaDataEmit::D efinetyperefbyname](imetadataemit-definetyperefbyname-method.md) o [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md) para crear una referencia de tipo, en el ámbito actual, para la clase primaria o la interfaz primaria del miembro.  
  
- Si el miembro de destino es una variable global o una función global (es decir, no es un miembro de una clase o interfaz), use el método [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md) para crear una referencia de módulo, en el ámbito actual, para el módulo primario del miembro.  
  
- Si el elemento primario del miembro de destino se resolverá más adelante mediante el compilador o el vinculador, pase `mdTokenNil` `tkParent` . El único escenario en el que esto se aplica es cuando se importa una función global o una variable global desde un archivo. obj que se vinculará en última instancia al módulo actual y los metadatos combinados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
