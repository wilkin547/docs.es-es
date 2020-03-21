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
ms.openlocfilehash: 53b3d94e8b1e273fcbc041d25a5bf586a12735c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177251"
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod (Método)
Obtiene un puntero al token MethodDef para el método incluido <xref:System.Type> en el especificado y que tiene el nombre y la firma de metadatos especificados.  
  
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
 [en] El `mdTypeDef` token para el tipo (una clase o interfaz) que encierra el miembro que se va a buscar. Si este `mdTokenNil`valor es , la búsqueda se realiza para una función global.  
  
 `szName`  
 [en] El nombre del método que se va a buscar.  
  
 `pvSigBlob`  
 [en] Un puntero a la firma de metadatos binarios del método.  
  
 `cbSigBlob`  
 [en] El tamaño en `pvSigBlob`bytes de .  
  
 `pmb`  
 [fuera] Un puntero al token MethodDef coincidente.  
  
## <a name="remarks"></a>Observaciones  
 El método se especifica utilizando su`td`clase o`szName`interfaz envolvente (`pvSigBlob`), su nombre ( ) y, opcionalmente, su firma ( ). Puede haber varios métodos con el mismo nombre en una clase o interfaz. En ese caso, pase la firma del método para encontrar la coincidencia única.  
  
 La firma `FindMethod` que se pasa debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede incrustar un token que identifica la clase envolvente o el tipo de valor. El token es un índice en la tabla TypeDef local. No puede crear una firma en tiempo de ejecución fuera del contexto `FindMethod`del ámbito actual y usar esa firma como entrada para introducir .  
  
 `FindMethod`encuentra sólo los métodos que se definieron directamente en la clase o interfaz; no encuentra métodos heredados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Reflection.MethodInfo>
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
