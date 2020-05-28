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
ms.openlocfilehash: ef6f7a1a6e86b45acce91792385bc3761dfb4c39
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009085"
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
 [in] Nombre del recurso.  
  
 `ptkManifestResource`  
 enuncia Matriz que se usa para almacenar los `mdManifestResource` tokens de metadatos, cada uno de los cuales representa un recurso de manifiesto.  
  
## <a name="remarks"></a>Comentarios  
 El `FindManifestResourceByName` método utiliza las reglas estándar empleadas por el Common Language Runtime para resolver las referencias.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../deployment/how-the-runtime-locates-assemblies.md)
