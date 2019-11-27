---
title: IMetaDataImport::FindField (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 842d6c0deb90bc45cb59454fb30fcc3544d742f1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437940"
---
# <a name="imetadataimportfindfield-method"></a>IMetaDataImport::FindField (Método)
Obtiene un puntero al token de FieldDef para el campo incluido en el <xref:System.Type> especificado y que tiene el nombre y la firma de metadatos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `td`  
 de El token TypeDef de la clase o interfaz que incluye el campo que se va a buscar. Si este valor se `mdTokenNil`, la búsqueda se realiza para una variable global.  
  
 `szName`  
 de Nombre del campo que se va a buscar.  
  
 `pvSigBlob`  
 de Puntero a la firma de metadatos binarios del campo.  
  
 `cbSigBlob`  
 de Tamaño en bytes de `pvSigBlob`.  
  
 `pmb`  
 enuncia Puntero al token de FieldDef coincidente.  
  
## <a name="remarks"></a>Comentarios  
 Especifique el campo mediante su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`).  
  
 La firma pasada a `FindField` debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor. (El token es un índice en la tabla TypeDef local). No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para `FindField`.  
  
 `FindField` encuentra solo los campos que se definieron directamente en la clase o la interfaz; no se encuentran los campos heredados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
