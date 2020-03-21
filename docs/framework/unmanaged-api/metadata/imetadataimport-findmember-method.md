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
ms.openlocfilehash: dab155b82d87609b3d3f390133e6490502a43518
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177281"
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember (Método)
Obtiene un puntero al token MemberDef para el campo o <xref:System.Type> método que está incluido en el especificado y que tiene el nombre especificado y la firma de metadatos.  
  
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
 [en] El token TypeDef para la clase o interfaz que encierra el miembro que se va a buscar. Si este `mdTokenNil`valor es , la búsqueda se realiza para una variable global o una función global.  
  
 `szName`  
 [en] El nombre del miembro que se va a buscar.  
  
 `pvSigBlob`  
 [en] Un puntero a la firma de metadatos binarios del miembro.  
  
 `cbSigBlob`  
 [en] El tamaño en `pvSigBlob`bytes de .  
  
 `pmb`  
 [fuera] Un puntero al token MemberDef coincidente.  
  
## <a name="remarks"></a>Observaciones  
 El miembro se especifica utilizando su`td`clase o`szName`interfaz envolvente (`pvSigBlob`), su nombre ( ) y, opcionalmente, su firma ( ). Puede haber varios miembros con el mismo nombre en una clase o interfaz. En ese caso, pase la firma del miembro para encontrar la coincidencia única.  
  
 La firma `FindMember` que se pasa debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede incrustar un token que identifica la clase envolvente o el tipo de valor. El token es un índice en la tabla TypeDef local. No puede crear una firma en tiempo de ejecución fuera del contexto `FindMember`del ámbito actual y usar esa firma como entrada para introducir .  
  
 `FindMember`encuentra solo los miembros que se definieron directamente en la clase o interfaz; no encuentra miembros heredados.  
  
> [!NOTE]
> `FindMember`es un método auxiliar. Llama a [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); si esa llamada no `FindMember` encuentra una coincidencia, llama a [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
