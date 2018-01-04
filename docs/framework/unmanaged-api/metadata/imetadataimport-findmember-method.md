---
title: "IMetaDataImport::FindMember (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMember
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a20930688aed210309a719de2c7187f1f5fd1f24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember (Método)
Obtiene un puntero al MemberDef símbolo (token) de campo o un método que se encierra entre según los valores especificados <xref:System.Type> y que tiene la firma de nombre y los metadatos especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `td`  
 [in] El token de TypeDef para la clase o interfaz que incluye el miembro que se va a buscar. Si este valor es `mdTokenNil`, la búsqueda se realiza para una variable global o una función global.  
  
 `szName`  
 [in] El nombre del miembro que se va a buscar.  
  
 `pvSigBlob`  
 [in] Un puntero a la firma de metadatos binaria del miembro.  
  
 `cbSigBlob`  
 [in] El tamaño en bytes de `pvSigBlob`.  
  
 `pmb`  
 [out] Un puntero al token MemberDef coincidente.  
  
## <a name="remarks"></a>Comentarios  
 Especificar el miembro con su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`). Puede haber varios miembros con el mismo nombre en una clase o interfaz. En ese caso, pase la firma del miembro para encontrar a una coincidencia única.  
  
 La firma se pasa a `FindMember` deben haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede incrustar un símbolo (token) que identifica el tipo de valor o clase envolvente. El token es un índice en la tabla TypeDef local. No se puede compilar una firma en tiempo de ejecución fuera del contexto del ámbito actual y use esa firma como entrada a `FindMember`.  
  
 `FindMember`busca a solo los miembros que se definieron directamente en la clase o interfaz; Si no encuentra los miembros heredados.  
  
> [!NOTE]
>  `FindMember`es un método auxiliar. Llama [IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); si esa llamada no encuentra una coincidencia, `FindMember` , a continuación, se llama [FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
