---
title: IMetaDataImport::FindMember (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
ms.openlocfilehash: bcd9499d0aef34fb34065ed58c0f0d69cc4ecedc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711447"
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember (Método)

Obtiene un puntero al token de MemberDef para el campo o método que está incluido en el especificado <xref:System.Type> y que tiene el nombre y la firma de metadatos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `td`  
 de El token TypeDef de la clase o interfaz que incluye el miembro que se va a buscar. Si este valor es `mdTokenNil` , la búsqueda se realiza para una variable global o una función global.  
  
 `szName`  
 de Nombre del miembro que se va a buscar.  
  
 `pvSigBlob`  
 de Puntero a la firma de metadatos binarios del miembro.  
  
 `cbSigBlob`  
 de Tamaño en bytes de `pvSigBlob` .  
  
 `pmb`  
 enuncia Puntero al token de MemberDef coincidente.  
  
## <a name="remarks"></a>Comentarios  

 El miembro se especifica mediante su clase o interfaz envolvente ( `td` ), su nombre ( `szName` ) y, opcionalmente, su firma ( `pvSigBlob` ). Puede haber varios miembros con el mismo nombre en una clase o interfaz. En ese caso, pase la Signatura del miembro para encontrar la coincidencia única.  
  
 La firma que se pasa a `FindMember` debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor. El token es un índice en la tabla TypeDef local. No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para la entrada a `FindMember` .  
  
 `FindMember` busca solo los miembros que se definieron directamente en la clase o la interfaz; no se encuentran los miembros heredados.  
  
> [!NOTE]
> `FindMember` es un método auxiliar. Llama a [IMetaDataImport:: findMethod (](imetadataimport-findmethod-method.md); Si esa llamada no encuentra ninguna coincidencia, `FindMember` llama a [IMetaDataImport:: FindField (](imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
