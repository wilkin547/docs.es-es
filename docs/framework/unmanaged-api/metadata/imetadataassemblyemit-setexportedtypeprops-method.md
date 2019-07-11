---
title: IMetaDataAssemblyEmit::SetExportedTypeProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e4be840760782789aa91e5519f60374aca2e3941
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775263"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a>IMetaDataAssemblyEmit::SetExportedTypeProps (Método)
Modifica la estructura de metadatos `ExportedType` especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ct`  
 [in] El token de metadatos que especifica el `ExportedType` estructura de metadatos que se puede modificar.  
  
 `tkImplementation`  
 [in] El token de tipo `File`, `AssemblyRef`, o `ExportedType`, que especifica cómo se implementa este tipo.  
  
 `tkTypeDef`  
 [in] El `TypeDef` token al que hace referencia en el archivo de código.  
  
 `dwExportedTypeFlags`  
 [in] Una combinación bit a bit de valores que especifican los atributos del tipo.  
  
## <a name="remarks"></a>Comentarios  
 Para crear un `ExportedType` estructura de los metadatos, use el [IMetaDataAssemblyEmit:: DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
