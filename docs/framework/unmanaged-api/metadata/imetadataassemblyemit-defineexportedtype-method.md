---
title: IMetaDataAssemblyEmit::DefineExportedType (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
ms.openlocfilehash: 44f97ef498eb8e64c55fc86b9f290b9e088293f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432069"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>IMetaDataAssemblyEmit::DefineExportedType (Método)
Crea una estructura `ExportedType` que contiene los metadatos para el tipo exportado especificado y devuelve el token de metadatos asociado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `szName`  
 de Nombre del tipo que se va a exportar. En la versión 1,1 del Common Language Runtime, el nombre del tipo exportado debe coincidir exactamente con el nombre especificado en el `TypeDef` para el tipo.  
  
 `tkImplementation`  
 de Token que especifica dónde se implementa el tipo exportado. Los valores válidos y sus significados asociados son:  
  
- `mdFile` el tipo se implementa en un archivo diferente dentro de este ensamblado.  
  
- `mdAssemblyRef` el tipo se implementa en un ensamblado diferente.  
  
- `mdExportedTYpe` el tipo está anidado dentro de otro tipo.  
  
- `mdFileNil` el tipo está en el mismo archivo que el manifiesto y no es un tipo anidado.  
  
 `tkTypeDef`  
 de Token a los metadatos que especifica el tipo que se va a exportar. Este valor se especifica en la tabla `TypeDef` del archivo que implementa el tipo y solo es relevante si ese archivo está en este ensamblado.  
  
 `dwExportedTypeFlags`  
 de Combinación bit a bit de los valores de enumeración de [cortypeattr (](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) que definen los valores de propiedad para el tipo exportado.  
  
 `pmdct`  
 enuncia Puntero al símbolo (token) de metadatos devuelto que indica el tipo exportado.  
  
## <a name="remarks"></a>Comentarios  
 Se debe definir una estructura de metadatos de `ExportedType` para cada tipo expuesto por este ensamblado y que se implementa en un módulo distinto del que contiene el manifiesto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
