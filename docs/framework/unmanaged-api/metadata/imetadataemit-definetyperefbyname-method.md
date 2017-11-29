---
title: "IMetaDataEmit::DefineTypeRefByName (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeRefByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9ce04733fa9f149f155d850c53b65b263943cf8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>IMetaDataEmit::DefineTypeRefByName (Método)
Obtiene metadatos de un token para un tipo que se define en el ámbito especificado, que se encuentra fuera del ámbito actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `tkResolutionScope`  
 [in] El token de especificar el ámbito de resolución. Los siguientes tipos de token son válidos:  
  
-   `mdModuleRef`, si el tipo se define en el mismo ensamblado en el que se define el llamador.  
  
-   `mdAssemblyRef`, si el tipo se define en un ensamblado distinto de aquél en el que se define el llamador.  
  
-   `mdTypeRef`, si el tipo es un tipo anidado.  
  
-   `mdModule`, si el tipo se define en el mismo módulo donde se define el llamador.  
  
-   Es null, si el tipo está definido globalmente.  
  
 `szName`  
 [in] El nombre del tipo de destino en Unicode.  
  
 `ptr`  
 [out] Un puntero a la `mdTypeRef` símbolo (token) que se asigna al tipo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
