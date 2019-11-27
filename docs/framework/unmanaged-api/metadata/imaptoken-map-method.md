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
ms.openlocfilehash: fd362beb9f8fd7a1f2076eb6490a96c0358520e4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432149"
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
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMapToken (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
