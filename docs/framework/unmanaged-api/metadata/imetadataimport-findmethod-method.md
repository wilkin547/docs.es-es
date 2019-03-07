---
title: IMetaDataImport::FindMethod (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 857ea06ad8aba2a6de87bdf670ad0462a2f7dde1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487295"
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod (Método)
Obtiene un puntero a MethodDef token para el método que se incluye por especificado <xref:System.Type> y que tiene la firma de nombre y los metadatos especificada.  
  
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
  
## <a name="parameters"></a>Parámetros  
 `td`  
 [in] El `mdTypeDef` token para el tipo (una clase o interfaz) que incluye el miembro que se busca. Si este valor es `mdTokenNil`, a continuación, la búsqueda se realiza para una función global.  
  
 `szName`  
 [in] El nombre del método que se busca.  
  
 `pvSigBlob`  
 [in] Un puntero a la firma de metadatos binaria del método.  
  
 `cbSigBlob`  
 [in] El tamaño en bytes de `pvSigBlob`.  
  
 `pmb`  
 [out] Un puntero al token MethodDef coincidente.  
  
## <a name="remarks"></a>Comentarios  
 Especifique el método con su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`). Puede haber varios métodos con el mismo nombre en una clase o interfaz. En ese caso, pase la firma del método para buscar a una coincidencia única.  
  
 La firma pasa a `FindMethod` deben haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede incrustar un token que identifica el tipo de valor o la clase envolvente. El token es un índice en la tabla TypeDef local. No se puede generar una firma de tiempo de ejecución fuera del contexto del ámbito actual y use esa firma como entrada a `FindMethod`.  
  
 `FindMethod` Busca solo los métodos que se definieron directamente en la clase o interfaz; no se encuentra métodos heredados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Reflection.MethodInfo>
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
