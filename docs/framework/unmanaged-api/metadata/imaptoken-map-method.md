---
title: IMapToken::Map (Método)
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
ms.openlocfilehash: 51cca1ab61027090b0d22781dfd740038bc9372d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718207"
---
# <a name="imaptokenmap-method"></a>IMapToken::Map (Método)

Asigna una relación entre los ensamblados mediante firmas de metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `tkImp`  
 de Token de metadatos que representa el objeto de código importado.  
  
 `tkEmit`  
 de Token de metadatos que representa el objeto de código emitido.  
  
## <a name="remarks"></a>Comentarios  

 Cuando se produce la reasignación del token durante una combinación, el ámbito del token original se encuentra en el ámbito de metadatos (origen) importado y el ámbito del nuevo token se encuentra en el ámbito de los metadatos emitidos (de destino).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMapToken (Interfaz)](imaptoken-interface.md)
