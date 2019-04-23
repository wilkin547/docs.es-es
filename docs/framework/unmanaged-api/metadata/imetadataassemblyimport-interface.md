---
title: IMetaDataAssemblyImport (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 373ff0470e2403f91534df0c0ffe4039dbb0f832
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112637"
---
# <a name="imetadataassemblyimport-interface"></a>IMetaDataAssemblyImport (Interfaz)
Proporciona métodos para acceder al contenido de un manifiesto del ensamblado y examinarlo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CloseEnum (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|Libera el identificador del enumerador especificado.|  
|[EnumAssemblyRefs (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|Obtiene un puntero de interfaz a un enumerador que contiene el `mdAssemblyRef` tokens de los ensamblados que se hace referencia el ensamblado en el ámbito de metadatos actual.|  
|[EnumExportedTypes (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|Obtiene un puntero de interfaz a un enumerador que contiene el `mdExportedType` tokens de los tipos COM al que hace referencia el ensamblado en el ámbito de metadatos actual.|  
|[EnumFiles (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|Obtiene un puntero de interfaz a un enumerador que contiene el `mdFile` tokens de los archivos al que hace referencia el ensamblado en el ámbito de metadatos actual.|  
|[EnumManifestResources (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|Obtiene un puntero de interfaz a un enumerador que contiene el `mdManifestResource` tokens de los recursos al que hace referencia el ensamblado en el ámbito de metadatos actual.|  
|[FindAssembliesByName (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|Obtiene una matriz de `mdAssemblyRef` tokens para los ensamblados con el nombre especificado.|  
|[FindExportedTypeByName (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|Obtiene un `mdExportedType` token para el tipo COM con el nombre especificado.|  
|[FindManifestResourceByName (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|Obtiene un `mdManifestResource` token para el recurso con el nombre especificado.|  
|[GetAssemblyFromScope (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|Obtiene el token para el ensamblado en el ámbito de metadatos actual.|  
|[GetAssemblyProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|Obtiene los valores de propiedad del ensamblado especificado.|  
|[GetAssemblyRefProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|Obtiene los valores de propiedad del elemento especificado `mdAssemblyRef` token.|  
|[GetExportedTypeProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|Obtiene los valores de propiedad del tipo COM especificado.|  
|[GetFileProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|Obtiene los valores de propiedad del archivo especificado.|  
|[GetManifestResourceProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|Obtiene los valores de propiedad del recurso del manifiesto especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
