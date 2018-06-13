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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3736d604b7e77028a2b99d462d88ae207df926c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448028"
---
# <a name="imetadataimportfindmemberref-method"></a>IMetaDataImport::FindMemberRef (Método)
Obtiene un puntero al token MemberRef para el miembro de referencia que es delimitadas por especificado <xref:System.Type> y que tiene la firma de nombre y los metadatos especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `td`  
 [in] Símbolo (token) de TypeRef para la clase o interfaz que incluye la referencia de miembro que se busca. Si este valor es `mdTokenNil`, la búsqueda se realiza para una variable global o una referencia de función global.  
  
 `szName`  
 [in] El nombre de la referencia de miembro que se busca.  
  
 `pvSigBlob`  
 [in] Un puntero a la firma de metadatos binaria de la referencia de miembro.  
  
 `cbSigBlob`  
 [in] El tamaño en bytes de `pvSigBlob`.  
  
 `pmr`  
 [out] Un puntero al token MemberRef coincidente.  
  
## <a name="remarks"></a>Comentarios  
 Especificar el miembro con su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`).  
  
 La firma se pasa a `FindMemberRef` deben haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede incrustar un símbolo (token) que identifica el tipo de valor o clase envolvente. El token es un índice en la tabla TypeDef local. No se puede compilar una firma en tiempo de ejecución fuera del contexto del ámbito actual y utilizar esa firma como entrada para `FindMemberRef`.  
  
 `FindMemberRef` Busca solo las referencias de miembro que se definieron directamente en la clase o interfaz; Si no encuentra referencias de miembro heredadas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
