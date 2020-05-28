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
ms.openlocfilehash: 7babd0a90b9882acb03b6360753f55c57a399b9e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005640"
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
 de Token de la clase o interfaz de destino. Este es un `mdTypeDef` token o `mdTypeDefNil` .  
  
 `szEvent`  
 [in] Nombre del evento.  
  
 `dwEventFlags`  
 de Marcas de evento.  
  
 `tkEventType`  
 de El token para la clase de evento. Se trata de un `mdTypeDef` , un `mdTypeRef` o un `mdTokenNil` token.  
  
 `mdAddOn`  
 de Método utilizado para suscribirse al evento o null.  
  
 `mdRemoveOn`  
 de Método utilizado para cancelar la suscripción al evento o null.  
  
 `mdFire`  
 de Método utilizado (por una clase derivada) para generar el evento.  
  
 `rmdOtherMethods[]`  
 de Matriz de tokens para otros métodos asociados al evento. La matriz se termina con un `mdMethodDefNil` token.  
  
 `pmdEvent`  
 enuncia Símbolo (token) de metadatos asignado al evento.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
