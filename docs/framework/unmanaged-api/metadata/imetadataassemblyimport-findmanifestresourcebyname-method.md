---
title: IMetaDataAssemblyImport::FindManifestResourceByName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aaaae5bda88d1fbc9949a080c5765127fd112bde
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855957"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a>IMetaDataAssemblyImport::FindManifestResourceByName (Método)
Obtiene un puntero al recurso de manifiesto con el nombre especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
## <a name="parameters"></a>Parámetros  
 `szName`  
 de Nombre del recurso.  
  
 `ptkManifestResource`  
 enuncia Matriz que se usa para almacenar `mdManifestResource` los tokens de metadatos, cada uno de los cuales representa un recurso de manifiesto.  
  
## <a name="remarks"></a>Comentarios  
 El `FindManifestResourceByName` método utiliza las reglas estándar empleadas por el Common Language Runtime para resolver las referencias.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor. h  
  
 **Biblioteca** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
