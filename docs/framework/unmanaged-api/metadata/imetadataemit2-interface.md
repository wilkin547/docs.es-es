---
title: IMetaDataEmit2 (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 87b5b60d75d5d28e100ec75192d0cacf51765927
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200199"
---
# <a name="imetadataemit2-interface"></a>IMetaDataEmit2 (Interfaz)
Extiende la [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaz principalmente para proporcionar la capacidad de trabajar con tipos genéricos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|Crea una definición para un parámetro de tipo genérico y obtiene un token para ese parámetro de tipo genérico.|  
|[Método DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|Crea una instancia de un método genérica y obtiene un token a la definición.|  
|[Método GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|Obtiene un valor que indica la diferencia de tamaño de los datos que es necesaria para expresar los cambios para la sesión actual de editar y continuar.|  
|[Método ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|Restablece el registro de editar y continuar e inicia una nueva sesión.|  
|[Método SaveDelta](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|Guarda los cambios de la sesión actual de editar y continuar en el archivo especificado.|  
|[Método SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|Guarda los cambios de la sesión actual de editar y continuar en la memoria.|  
|[Método SaveDeltaToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|Guarda los cambios de la sesión actual de editar y continuar en la secuencia especificada.|  
|[Método SetGenericParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|Establece los valores de propiedad de la definición de parámetro genérico al que hace referencia el token especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
