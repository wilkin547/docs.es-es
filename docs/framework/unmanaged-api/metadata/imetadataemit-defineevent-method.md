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
ms.openlocfilehash: a9598be850604f16ee8cc62187e1fed7ecf3a7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175855"
---
# <a name="imetadataemitdefineevent-method"></a>IMetaDataEmit::DefineEvent (Método)
Crea una definición para un evento con la firma de metadatos especificada y obtiene un token a esa definición de evento.  
  
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
 [en] El token para la clase o interfaz de destino. Esto es `mdTypeDef` un `mdTypeDefNil` token o un token.  
  
 `szEvent`  
 [in] Nombre del evento.  
  
 `dwEventFlags`  
 [en] Indicadores de eventos.  
  
 `tkEventType`  
 [en] El token de la clase de evento. Se trata `mdTypeDef`de `mdTypeRef`un `mdTokenNil` token , a o un token.  
  
 `mdAddOn`  
 [en] El método utilizado para suscribirse al evento, o null.  
  
 `mdRemoveOn`  
 [en] El método utilizado para cancelar la suscripción al evento, o null.  
  
 `mdFire`  
 [en] El método utilizado (por una clase derivada) para generar el evento.  
  
 `rmdOtherMethods[]`  
 [en] Matriz de tokens para otros métodos asociados al evento. La matriz se termina `mdMethodDefNil` con un token.  
  
 `pmdEvent`  
 [fuera] El token de metadatos asignado al evento.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
