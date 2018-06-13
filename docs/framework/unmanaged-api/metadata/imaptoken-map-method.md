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
ms.openlocfilehash: f2633bfadaabf208a2b86fda83375c3a136b93b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448177"
---
# <a name="imaptokenmap-method"></a>IMapToken::Map (Método)
Asigna una relación entre los ensamblados utilizando firmas de metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `tkImp`  
 [in] El token de metadatos que representa el objeto de código importado.  
  
 `tkEmit`  
 [in] El token de metadatos que representa el objeto de código emitido.  
  
## <a name="remarks"></a>Comentarios  
 Cuando el token volver a asignar se produce durante una mezcla, el token original tiene un ámbito en el ámbito de metadatos importados (origen) y el nuevo token tiene un ámbito en el ámbito de metadatos emitido (destino).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMapToken (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
