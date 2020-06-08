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
ms.openlocfilehash: 11ea6e468909ea42e38bdc7b76c60c460c98025e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503672"
---
# <a name="imetadataimportfindfield-method"></a>IMetaDataImport::FindField (Método)
Obtiene un puntero al token de FieldDef para el campo incluido en el especificado <xref:System.Type> y que tiene el nombre y la firma de metadatos especificados.  
  
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
 de El token TypeDef de la clase o interfaz que incluye el campo que se va a buscar. Si este valor es `mdTokenNil` , la búsqueda se realiza para una variable global.  
  
 `szName`  
 de Nombre del campo que se va a buscar.  
  
 `pvSigBlob`  
 de Puntero a la firma de metadatos binarios del campo.  
  
 `cbSigBlob`  
 de Tamaño en bytes de `pvSigBlob` .  
  
 `pmb`  
 enuncia Puntero al token de FieldDef coincidente.  
  
## <a name="remarks"></a>Comentarios  
 Especifique el campo mediante su clase o interfaz envolvente ( `td` ), su nombre ( `szName` ) y, opcionalmente, su firma ( `pvSigBlob` ).  
  
 La firma que se pasa a `FindField` debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor. (El token es un índice en la tabla TypeDef local). No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para `FindField` .  
  
 `FindField`busca solo los campos que se definieron directamente en la clase o la interfaz; no se encuentran los campos heredados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
