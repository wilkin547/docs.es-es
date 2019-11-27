---
title: IMetaDataEmit::DefineEvent (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: 6966d0ad2fefd8401b19d8e8dcf7776799a066b2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432568"
---
# <a name="imetadataemitdefineevent-method"></a>IMetaDataEmit::DefineEvent (Método)
Crea una definición para un evento con la firma de metadatos especificada y obtiene un token para esa definición de evento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `td`  
 de Token de la clase o interfaz de destino. Se trata de un token de `mdTypeDef` o `mdTypeDefNil`.  
  
 `szEvent`  
 de Nombre del evento.  
  
 `dwEventFlags`  
 de Marcas de evento.  
  
 `tkEventType`  
 de El token para la clase de evento. Se trata de una `mdTypeDef`, un `mdTypeRef`o un token de `mdTokenNil`.  
  
 `mdAddOn`  
 de Método utilizado para suscribirse al evento o null.  
  
 `mdRemoveOn`  
 de Método utilizado para cancelar la suscripción al evento o null.  
  
 `mdFire`  
 de Método utilizado (por una clase derivada) para generar el evento.  
  
 `rmdOtherMethods[]`  
 de Matriz de tokens para otros métodos asociados al evento. La matriz finaliza con un token de `mdMethodDefNil`.  
  
 `pmdEvent`  
 enuncia Símbolo (token) de metadatos asignado al evento.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
