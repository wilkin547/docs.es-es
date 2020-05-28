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
ms.openlocfilehash: b6ca7c619d32e69ffac20b80561171d0320db2d4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008383"
---
# <a name="imetadataconverter-interface"></a>IMetaDataConverter (Interfaz)
Proporciona métodos para asignar las bibliotecas de tipos a sus firmas de metadatos y para convertirlas de uno a otro.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetMetaDataFromTypeInfo](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|Obtiene un puntero a una instancia de [IMetaDataImport](imetadataimport-interface.md) que representa la firma de metadatos para la biblioteca de tipos a la que hace referencia la instancia de especificada `ITypeInfo` .|  
|[Método GetMetaDataFromTypeLib](imetadataconverter-getmetadatafromtypelib-method.md)|Obtiene un puntero a una `IMetaDataImport` instancia de que representa la firma de metadatos para la biblioteca de tipos representada por la instancia de especificada `ITypeLib` .|  
|[Método GetTypeLibFromMetaData](imetadataconverter-gettypelibfrommetadata-method.md)|Obtiene un puntero a una `ITypeLib` instancia de que representa la biblioteca de tipos que tiene los nombres de módulo y de biblioteca especificados.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de metadatos](metadata-interfaces.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
