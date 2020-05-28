---
title: IMetaDataEmit::SetEventProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
ms.openlocfilehash: 720133e64c02aa09c9ff7e43a20630b0d55c1acf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008760"
---
# <a name="imetadataemitseteventprops-method"></a>IMetaDataEmit::SetEventProps (Método)
Establece o actualiza la característica especificada de un evento definido por una llamada anterior a [IMetaDataEmit::D efineevent](imetadataemit-defineevent-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,
    [in]  DWORD       dwEventFlags,
    [in]  mdToken     tkEventType,
    [in]  mdMethodDef mdAddOn,
    [in]  mdMethodDef mdRemoveOn,
    [in]  mdMethodDef mdFire,
    [in]  mdMethodDef rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ev`  
 de El token del evento.  
  
 `dwEventFlags`  
 de Marcas de evento. Se trata de una máscara de máscara de `CorEventAttr` valores.  
  
 `tkEventType`  
 de El token para la clase de evento. Este es un `mdTypeDef` `mdTypeRef` token o.  
  
 `mdAddOn`  
 de Método utilizado para suscribirse al evento o null.  
  
 `mdRemoveOn`  
 de Método utilizado para cancelar la suscripción al evento o null.  
  
 `mdFire`  
 de Método utilizado (por una clase derivada) para generar el evento.  
  
 `rmdOtherMethods[]`  
 de Matriz de tokens para otros métodos asociados al evento. El último elemento de la matriz debe ser `mdMethodDefNil` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
