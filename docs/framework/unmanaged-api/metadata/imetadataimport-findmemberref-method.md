---
title: IMetaDataImport::FindMemberRef (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
ms.openlocfilehash: d8b8bfd0e70e75c702f32555c10f433a1ff4ae10
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175426"
---
# <a name="imetadataimportfindmemberref-method"></a>IMetaDataImport::FindMemberRef (Método)
Obtiene un puntero al token MemberRef para la referencia de <xref:System.Type> miembro que está delimitada por el especificado y que tiene el nombre especificado y la firma de metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `td`  
 [en] El token TypeRef para la clase o interfaz que encierra la referencia de miembro que se va a buscar. Si este `mdTokenNil`valor es , la búsqueda se realiza para una variable global o una referencia de función global.  
  
 `szName`  
 [en] El nombre de la referencia de miembro que se va a buscar.  
  
 `pvSigBlob`  
 [en] Un puntero a la firma de metadatos binarios de la referencia de miembro.  
  
 `cbSigBlob`  
 [en] El tamaño en `pvSigBlob`bytes de .  
  
 `pmr`  
 [fuera] Un puntero al token MemberRef coincidente.  
  
## <a name="remarks"></a>Observaciones  
 El miembro se especifica utilizando su`td`clase o`szName`interfaz envolvente (`pvSigBlob`), su nombre ( ) y, opcionalmente, su firma ( ).  
  
 La firma `FindMemberRef` que se pasa debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede incrustar un token que identifica la clase envolvente o el tipo de valor. El token es un índice en la tabla TypeDef local. No puede crear una firma en tiempo de ejecución fuera del `FindMemberRef`contexto del ámbito actual y usar esa firma como entrada para .  
  
 `FindMemberRef`encuentra solo las referencias de miembro que se definieron directamente en la clase o interfaz; no encuentra referencias de miembros heredadas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
