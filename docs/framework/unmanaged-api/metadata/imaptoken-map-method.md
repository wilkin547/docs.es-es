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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8ac12d5b6bc2911e3bd879285a9a12f65c426f0d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745857"
---
# <a name="imaptokenmap-method"></a>IMapToken::Map (Método)
Asigna una relación entre los ensamblados utilizando firmas de metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `tkImp`  
 [in] El token de metadatos que representa el objeto de código importados.  
  
 `tkEmit`  
 [in] El token de metadatos que representa el objeto de código emitido.  
  
## <a name="remarks"></a>Comentarios  
 Cuando el token volver a asignar se produce durante una combinación, el token original se limita el ámbito de metadatos importados (origen) y el nuevo token se enfoca en el ámbito de metadatos emitido (destino).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMapToken (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
