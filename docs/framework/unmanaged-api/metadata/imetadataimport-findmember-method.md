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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4eefb7ec1e7d0d130ec64531a59d1d5bbce04963
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968927"
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember (Método)
Obtiene un puntero al token de MemberDef para el campo o método que está incluido en el <xref:System.Type> especificado y que tiene el nombre y la firma de metadatos especificados.  
  
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
 de El token TypeDef de la clase o interfaz que incluye el miembro que se va a buscar. Si este valor es `mdTokenNil`, la búsqueda se realiza para una variable global o una función global.  
  
 `szName`  
 de Nombre del miembro que se va a buscar.  
  
 `pvSigBlob`  
 de Puntero a la firma de metadatos binarios del miembro.  
  
 `cbSigBlob`  
 de Tamaño en bytes de `pvSigBlob`.  
  
 `pmb`  
 enuncia Puntero al token de MemberDef coincidente.  
  
## <a name="remarks"></a>Comentarios  
 El miembro se especifica mediante su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`). Puede haber varios miembros con el mismo nombre en una clase o interfaz. En ese caso, pase la Signatura del miembro para encontrar la coincidencia única.  
  
 La firma que se `FindMember` pasa a debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor. El token es un índice en la tabla TypeDef local. No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para la `FindMember`entrada a.  
  
 `FindMember`busca solo los miembros que se definieron directamente en la clase o la interfaz; no se encuentran los miembros heredados.  
  
> [!NOTE]
> `FindMember`es un método auxiliar. Llama a [IMetaDataImport:: findMethod (](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Si esa llamada no encuentra ninguna coincidencia, `FindMember` llama a [IMetaDataImport:: FindField (](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor. h  
  
 **Biblioteca** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
