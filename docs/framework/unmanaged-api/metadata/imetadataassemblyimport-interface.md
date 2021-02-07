---
description: 'Más información acerca de: interfaz IMetaDataAssemblyImport'
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
ms.openlocfilehash: bb9c5163e4f5b68700e5a3836fa55edbbebac01c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753645"
---
# <a name="imetadataassemblyimport-interface"></a>IMetaDataAssemblyImport (Interfaz)

Proporciona métodos para acceder al contenido de un manifiesto del ensamblado y examinarlo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CloseEnum (Método)](imetadataassemblyimport-closeenum-method.md)|Libera el identificador del enumerador especificado.|  
|[Método EnumAssemblyRefs](imetadataassemblyimport-enumassemblyrefs-method.md)|Obtiene un puntero de interfaz a un enumerador que contiene los `mdAssemblyRef` tokens de los ensamblados a los que hace referencia el ensamblado en el ámbito de metadatos actual.|  
|[Método EnumExportedTypes](imetadataassemblyimport-enumexportedtypes-method.md)|Obtiene un puntero de interfaz a un enumerador que contiene los `mdExportedType` tokens de los tipos com a los que hace referencia el ensamblado en el ámbito de metadatos actual.|  
|[Método EnumFiles](imetadataassemblyimport-enumfiles-method.md)|Obtiene un puntero de interfaz a un enumerador que contiene los `mdFile` tokens de los archivos a los que hace referencia el ensamblado en el ámbito de metadatos actual.|  
|[Método EnumManifestResources](imetadataassemblyimport-enummanifestresources-method.md)|Obtiene un puntero de interfaz a un enumerador que contiene los `mdManifestResource` tokens de los recursos a los que hace referencia el ensamblado en el ámbito de metadatos actual.|  
|[Método FindAssembliesByName](imetadataassemblyimport-findassembliesbyname-method.md)|Obtiene una matriz de `mdAssemblyRef` tokens para los ensamblados con el nombre especificado.|  
|[Método FindExportedTypeByName](imetadataassemblyimport-findexportedtypebyname-method.md)|Obtiene un `mdExportedType` token para el tipo com con el nombre especificado.|  
|[Método FindManifestResourceByName](imetadataassemblyimport-findmanifestresourcebyname-method.md)|Obtiene un `mdManifestResource` token para el recurso con el nombre especificado.|  
|[Método GetAssemblyFromScope](imetadataassemblyimport-getassemblyfromscope-method.md)|Obtiene el token para el ensamblado en el ámbito de metadatos actual.|  
|[Método GetAssemblyProps](imetadataassemblyimport-getassemblyprops-method.md)|Obtiene los valores de propiedad del ensamblado especificado.|  
|[Método GetAssemblyRefProps](imetadataassemblyimport-getassemblyrefprops-method.md)|Obtiene los valores de propiedad del `mdAssemblyRef` token especificado.|  
|[Método GetExportedTypeProps](imetadataassemblyimport-getexportedtypeprops-method.md)|Obtiene los valores de propiedad del tipo COM especificado.|  
|[Método GetFileProps](imetadataassemblyimport-getfileprops-method.md)|Obtiene los valores de propiedad del archivo especificado.|  
|[Método GetManifestResourceProps](imetadataassemblyimport-getmanifestresourceprops-method.md)|Obtiene los valores de propiedad del recurso de manifiesto especificado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](metadata-interfaces.md)
- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
