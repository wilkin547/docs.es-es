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
ms.openlocfilehash: 28aa8313e7ba0c071187d0f1f6d78431b16fc005
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164806"
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
