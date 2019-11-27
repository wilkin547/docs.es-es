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
ms.openlocfilehash: 470b6511366cef1680eaf97f9ab376736add55c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437897"
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod (Método)
Obtiene un puntero al token MethodDef para el método incluido en el <xref:System.Type> especificado y que tiene el nombre y la firma de metadatos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de El token de `mdTypeDef` para el tipo (una clase o interfaz) que incluye el miembro que se va a buscar. Si este valor se `mdTokenNil`, la búsqueda se realiza para una función global.  
  
 `szName`  
 de Nombre del método que se va a buscar.  
  
 `pvSigBlob`  
 de Puntero a la firma de metadatos binarios del método.  
  
 `cbSigBlob`  
 de Tamaño en bytes de `pvSigBlob`.  
  
 `pmb`  
 enuncia Puntero al token MethodDef coincidente.  
  
## <a name="remarks"></a>Comentarios  
 El método se especifica mediante su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`). Puede haber varios métodos con el mismo nombre en una clase o interfaz. En ese caso, pase la Signatura del método para buscar la coincidencia única.  
  
 La firma pasada a `FindMethod` debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor. El token es un índice en la tabla TypeDef local. No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para la entrada en `FindMethod`.  
  
 `FindMethod` encuentra solo los métodos que se definieron directamente en la clase o la interfaz; no se encuentran los métodos heredados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Reflection.MethodInfo>
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
