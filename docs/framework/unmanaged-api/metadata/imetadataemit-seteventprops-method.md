---
title: "IMetaDataEmit::SetEventProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetEventProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8e2089c3f4b4e7677c2ddb9eabc8ee08cfd3695
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitseteventprops-method"></a>IMetaDataEmit::SetEventProps (Método)
Establece o actualiza la característica especificada de un evento definido por una llamada anterior a [IMetaDataEmit:: DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
#### <a name="parameters"></a>Parámetros  
 `ev`  
 [in] El token de evento.  
  
 `dwEventFlags`  
 [in] Marcas de evento. Se trata de una máscara de bits de `CorEventAttr` valores.  
  
 `tkEventType`  
 [in] El token para la clase de eventos. Esto es un `mdTypeDef` o un `mdTypeRef` símbolo (token).  
  
 `mdAddOn`  
 [in] El método utilizado para suscribirse al evento, o null.  
  
 `mdRemoveOn`  
 [in] El método utilizado para cancelar la suscripción al evento, o null.  
  
 `mdFire`  
 [in] El método utilizado (por una clase derivada) para generar el evento.  
  
 `rmdOtherMethods[]`  
 [in] Una matriz de símbolos (tokens) de otros métodos asociados al evento. El último elemento de la matriz debe ser `mdMethodDefNil`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
