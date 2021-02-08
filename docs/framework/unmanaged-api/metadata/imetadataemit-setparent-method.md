---
description: 'Más información acerca de: IMetaDataEmit:: SetParent (método)'
title: IMetaDataEmit::SetParent (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
ms.openlocfilehash: 9025d4a37de85a0e657059f63ef781dc4377c036
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772008"
---
# <a name="imetadataemitsetparent-method"></a>IMetaDataEmit::SetParent (Método)

Establece que el miembro especificado, tal como se define en una llamada anterior a [IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md), es un miembro del tipo especificado, tal como se define en una llamada anterior a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `mr`  
 de El `mdMemberRef` token para recibir un nuevo elemento primario.  
  
 `tk`  
 de `mdToken` Para el nuevo elemento primario.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
