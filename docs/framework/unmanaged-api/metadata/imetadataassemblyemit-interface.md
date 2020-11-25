---
title: IMetaDataAssemblyEmit (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
ms.openlocfilehash: 5d8bc54a94e1571ff8335c934407bbf235179ecc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728295"
---
# <a name="imetadataassemblyemit-interface"></a>IMetaDataAssemblyEmit (Interfaz)

Proporciona métodos que admiten el modelo autodescriptivo usado por Common Language Runtime para resolver y consumir recursos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método DefineAssembly](imetadataassemblyemit-defineassembly-method.md)|Crea una estructura de datos de ensamblado que contiene los metadatos para el ensamblado especificado y devuelve el token de metadatos asociado.|  
|[Método DefineAssemblyRef](imetadataassemblyemit-defineassemblyref-method.md)|Crea una estructura `AssemblyRef` que contiene los metadatos para el ensamblado al que este ensamblado hace referencia y devuelve el token de metadatos asociado.|  
|[Método DefineExportedType](imetadataassemblyemit-defineexportedtype-method.md)|Crea una estructura `ExportedType` que contiene los metadatos para el tipo exportado especificado y devuelve el token de metadatos asociado.|  
|[Método DefineFile](imetadataassemblyemit-definefile-method.md)|Crea una estructura de metadatos `File` que contiene los metadatos para el ensamblado al que se refiere este ensamblado y devuelve el token de metadatos asociado.|  
|[Método DefineManifestResource](imetadataassemblyemit-definemanifestresource-method.md)|Crea una estructura `ManifestResource` que contiene los metadatos para el recurso de manifiesto especificado y devuelve el token de metadatos asociado.|  
|[SetAssemblyProps (Método)](imetadataassemblyemit-setassemblyprops-method.md)|Modifica la estructura de metadatos `Assembly` especificada.|  
|[Método SetAssemblyRefProps](imetadataassemblyemit-setassemblyrefprops-method.md)|Modifica la estructura de metadatos `AssemblyRef` especificada.|  
|[Método SetExportedTypeProps](imetadataassemblyemit-setexportedtypeprops-method.md)|Modifica la estructura de metadatos `ExportedType` especificada.|  
|[Método SetFileProps](imetadataassemblyemit-setfileprops-method.md)|Modifica la estructura de metadatos `File` especificada.|  
|[Método SetManifestResourceProps](imetadataassemblyemit-setmanifestresourceprops-method.md)|Modifica la estructura de metadatos `ManifestResource` especificada.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de metadatos](metadata-interfaces.md)
- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
