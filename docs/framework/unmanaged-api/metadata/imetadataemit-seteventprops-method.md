---
description: 'Más información sobre: IMetaDataEmit:: SetEventProps ((método)'
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
ms.openlocfilehash: 888999bc0f80e82e0d139eecac7152a94104ed7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658133"
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
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
