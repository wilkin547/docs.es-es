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
ms.openlocfilehash: 75711b3d87699ff5db21a04351ff0acaccabb5aa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431864"
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
 de Una interfaz [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) que representa el ensamblado desde el que se importa el miembro de destino.  
  
 `pbHashValue`  
 de Una matriz que contiene el hash para el ensamblado especificado por `pAssemImport`.  
  
 `cbHashValue`  
 [in] Número de bytes en la matriz `pbHashValue`.  
  
 `pImport`  
 de Interfaz [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) que representa el ámbito de metadatos desde el que se importa el miembro de destino.  
  
 `mbMember`  
 de Token de metadatos que especifica el miembro de destino. El token puede ser un `mdMethodDef` (para un método de miembro), `mdProperty` (para una propiedad de miembro) o `mdFieldDef` (para un campo de miembro).  
  
 `pAssemEmit`  
 de Una interfaz [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) que representa el ensamblado en el que se importa el miembro de destino.  
  
 `tkParent`  
 de `mdTypeRef` o `mdModuleRef` token para el tipo o módulo, respectivamente, que posee el miembro de destino.  
  
 `pmr`  
 enuncia El token de `mdMemberRef` que se define en el ámbito actual para la referencia de miembro.  
  
## <a name="remarks"></a>Comentarios  
 El método `DefineImportMember` busca el miembro, especificado por `mbMember`, que se define en otro ámbito, especificado por `pImport`y recupera sus propiedades. Usa esta información para llamar al método [IMetaDataEmit::D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) en el ámbito actual para crear la referencia de miembro.  
  
 Normalmente, antes de utilizar el método `DefineImportMember`, debe crear, en el ámbito actual, una referencia de tipo o referencia de módulo para la clase primaria, la interfaz o el módulo del miembro de destino. El símbolo (token) de metadatos de esta referencia se pasa entonces en el argumento `tkParent`. No es necesario crear una referencia al elemento primario del miembro de destino si el compilador o el vinculador lo resolverán más adelante. En resumen:  
  
- Si el miembro de destino es un campo o un método, use el método [IMetaDataEmit::D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) o [IMetaDataEmit::D efineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) para crear una referencia de tipo, en el ámbito actual, para la clase primaria o la interfaz primaria del miembro.  
  
- Si el miembro de destino es una variable global o una función global (es decir, no es un miembro de una clase o interfaz), use el método [IMetaDataEmit::D efinemoduleref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) para crear una referencia de módulo, en el ámbito actual, para el módulo primario del miembro.  
  
- Si el elemento primario del miembro de destino se resolverá más adelante mediante el compilador o el vinculador, pase `mdTokenNil` en `tkParent`. El único escenario en el que esto se aplica es cuando se importa una función global o una variable global desde un archivo. obj que se vinculará en última instancia al módulo actual y los metadatos combinados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
