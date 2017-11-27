---
title: "EmbedResource (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EmbedResource
- EmbedResource
api_location: alink.dll
api_type: COM
f1_keywords: EmbedResource
helpviewer_keywords: EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 98dbd32452184bf4f832bd66ffebb0fcf3d5bb0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="embedresource-method"></a>EmbedResource (Método)
Declara un recurso incrustado. Este método no incrusta realmente el recurso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 Identificador del ensamblado.  
  
 `FileToken`  
 Símbolo (token) o ensamblado identificador del archivo que contiene el recurso.  
  
 `pszResourceName`  
 Nombre del recurso.  
  
 `dwOffset`  
 Desplazamiento del recurso de RVA.  
  
 `dwFlags`  
 Indicadores de accesibilidad como `mrPublic` y `mrPrivate`. Estas marcas se pueden pasar a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h.  
  
## <a name="see-also"></a>Vea también  
 [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
