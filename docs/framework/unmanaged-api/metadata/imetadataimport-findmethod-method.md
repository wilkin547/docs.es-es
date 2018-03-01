---
title: "IMetaDataImport::FindMethod (Método)"
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
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e59cc440ba004545c31d6b25d36cca4fdfb58899
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod (Método)
Obtiene un puntero al MethodDef token para el método que se encierra entre según los valores especificados <xref:System.Type> y que tiene la firma de nombre y los metadatos especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `td`  
 [in] El `mdTypeDef` token para el tipo (una clase o interfaz) que incluye el miembro que se va a buscar. Si este valor es `mdTokenNil`, a continuación, se realiza la búsqueda de una función global.  
  
 `szName`  
 [in] El nombre del método que se va a buscar.  
  
 `pvSigBlob`  
 [in] Un puntero a la firma de metadatos binaria del método.  
  
 `cbSigBlob`  
 [in] El tamaño en bytes de `pvSigBlob`.  
  
 `pmb`  
 [out] Un puntero al token MethodDef correspondiente.  
  
## <a name="remarks"></a>Comentarios  
 Especifique el método con su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`). Puede haber varios métodos con el mismo nombre en una clase o interfaz. En ese caso, pase la firma del método para encontrar a una coincidencia única.  
  
 La firma se pasa a `FindMethod` deben haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede incrustar un símbolo (token) que identifica el tipo de valor o clase envolvente. El token es un índice en la tabla TypeDef local. No se puede compilar una firma en tiempo de ejecución fuera del contexto del ámbito actual y use esa firma como entrada a `FindMethod`.  
  
 `FindMethod`busca únicamente los métodos que se definieron directamente en la clase o interfaz; no se encuentra métodos heredados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Reflection.MethodInfo>  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
