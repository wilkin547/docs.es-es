---
title: IMetaDataConverter (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: b771b368c069a4577d266b47bfb4a5ee1935e48e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436274"
---
# <a name="imetadataconverter-interface"></a>IMetaDataConverter (Interfaz)
Proporciona métodos para asignar las bibliotecas de tipos a sus firmas de metadatos y para convertirlas de uno a otro.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetMetaDataFromTypeInfo (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|Obtiene un puntero a una instancia de [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) que representa la firma de metadatos para la biblioteca de tipos a la que hace referencia la instancia de `ITypeInfo` especificada.|  
|[GetMetaDataFromTypeLib (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|Obtiene un puntero a una instancia de `IMetaDataImport` que representa la firma de metadatos para la biblioteca de tipos representada por la instancia de `ITypeLib` especificada.|  
|[GetTypeLibFromMetaData (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|Obtiene un puntero a una instancia de `ITypeLib` que representa la biblioteca de tipos que tiene los nombres de módulo y de biblioteca especificados.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
