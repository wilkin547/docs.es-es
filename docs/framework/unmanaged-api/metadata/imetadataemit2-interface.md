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
ms.openlocfilehash: 7ceae6f7713ab0eb1feff550838325df0ea52de2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447915"
---
# <a name="imetadataemit2-interface"></a>IMetaDataEmit2 (Interfaz)
Extiende la interfaz [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) principalmente para proporcionar la capacidad de trabajar con tipos genéricos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[DefineGenericParam (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|Crea una definición para un parámetro de tipo genérico y obtiene un token para ese parámetro de tipo genérico.|  
|[DefineMethodSpec (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|Crea una instancia genérica de un método y obtiene un token para la definición.|  
|[GetDeltaSaveSize (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|Obtiene un valor que indica la diferencia de tamaño de los datos necesarios para expresar los cambios de la sesión de edición y continuación actual.|  
|[ResetENCLog (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|Restablece el registro de edición y continuación e inicia una nueva sesión.|  
|[SaveDelta (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|Guarda los cambios de la sesión de edición y continuación actual en el archivo especificado.|  
|[SaveDeltaToMemory (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|Guarda los cambios de la sesión de edición y continuación actual en la memoria.|  
|[SaveDeltaToStream (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|Guarda los cambios de la sesión de edición y continuación actual en la secuencia especificada.|  
|[SetGenericParamProps (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|Establece los valores de propiedad para la definición de parámetro genérico a la que hace referencia el token especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
