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
ms.openlocfilehash: 506e13ad956a01b16e36d8c71737fe0efce4c01b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450319"
---
# <a name="imetadataemitseteventprops-method"></a>IMetaDataEmit::SetEventProps (Método)
Establece o actualiza la característica especificada de un evento definido por una llamada anterior a [IMetaDataEmit::D efineevent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).  
  
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
 de Marcas de evento. Se trata de una máscara de máscara de valores `CorEventAttr`.  
  
 `tkEventType`  
 de El token para la clase de evento. Se trata de un `mdTypeDef` o un token de `mdTypeRef`.  
  
 `mdAddOn`  
 de Método utilizado para suscribirse al evento o null.  
  
 `mdRemoveOn`  
 de Método utilizado para cancelar la suscripción al evento o null.  
  
 `mdFire`  
 de Método utilizado (por una clase derivada) para generar el evento.  
  
 `rmdOtherMethods[]`  
 de Matriz de tokens para otros métodos asociados al evento. El último elemento de la matriz se debe `mdMethodDefNil`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
