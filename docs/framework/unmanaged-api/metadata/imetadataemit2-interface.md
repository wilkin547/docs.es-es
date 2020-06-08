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
ms.openlocfilehash: 5a232f30da8812c6f3bd94647d74151312a8593b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493050"
---
# <a name="imetadataemit2-interface"></a>IMetaDataEmit2 (Interfaz)
Extiende la interfaz [IMetaDataEmit](imetadataemit-interface.md) principalmente para proporcionar la capacidad de trabajar con tipos genéricos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método DefineGenericParam](imetadataemit2-definegenericparam-method.md)|Crea una definición para un parámetro de tipo genérico y obtiene un token para ese parámetro de tipo genérico.|  
|[Método DefineMethodSpec](imetadataemit2-definemethodspec-method.md)|Crea una instancia genérica de un método y obtiene un token para la definición.|  
|[Método GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md)|Obtiene un valor que indica la diferencia de tamaño de los datos necesarios para expresar los cambios de la sesión de edición y continuación actual.|  
|[Método ResetENCLog](imetadataemit2-resetenclog-method.md)|Restablece el registro de edición y continuación e inicia una nueva sesión.|  
|[Método SaveDelta](imetadataemit2-savedelta-method.md)|Guarda los cambios de la sesión de edición y continuación actual en el archivo especificado.|  
|[Método SaveDeltaToMemory](imetadataemit2-savedeltatomemory-method.md)|Guarda los cambios de la sesión de edición y continuación actual en la memoria.|  
|[Método SaveDeltaToStream](imetadataemit2-savedeltatostream-method.md)|Guarda los cambios de la sesión de edición y continuación actual en la secuencia especificada.|  
|[Método SetGenericParamProps](imetadataemit2-setgenericparamprops-method.md)|Establece los valores de propiedad para la definición de parámetro genérico a la que hace referencia el token especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Interfaces de metadatos](metadata-interfaces.md)
- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
