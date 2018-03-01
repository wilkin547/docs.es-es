---
title: "IMetaDataImport::FindField (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3178d3ff3c64de5390e1150445f0c49c560aa32a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindfield-method"></a>IMetaDataImport::FindField (Método)
Obtiene un puntero a la FieldDef token para el campo que se encierra entre según los valores especificados <xref:System.Type> y que tiene la firma de nombre y los metadatos especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `td`  
 [in] El token de TypeDef para la clase o interfaz que incluye el campo que se busca. Si este valor es `mdTokenNil`, se realiza la búsqueda de una variable global.  
  
 `szName`  
 [in] El nombre del campo que se busca.  
  
 `pvSigBlob`  
 [in] Un puntero a la firma de metadatos binaria del campo.  
  
 `cbSigBlob`  
 [in] El tamaño en bytes de `pvSigBlob`.  
  
 `pmb`  
 [out] Un puntero al token de FieldDef correspondiente.  
  
## <a name="remarks"></a>Comentarios  
 Especifique el campo mediante su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`).  
  
 La firma se pasa a `FindField` deben haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede incrustar un símbolo (token) que identifica el tipo de valor o clase envolvente. (El token es un índice en la tabla TypeDef local). No se puede compilar una firma en tiempo de ejecución fuera del contexto del ámbito actual y utilizar esa firma como entrada para `FindField`.  
  
 `FindField`Busca solo los campos que se definieron directamente en la clase o interfaz; no se encuentra campos heredados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
