---
title: IMetaDataImport::GetRVA (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 126cc9d407e2653fdb3f4ea7b03fa05c24a572d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629132"
---
# <a name="imetadataimportgetrva-method"></a>IMetaDataImport::GetRVA (Método)
Obtiene la dirección virtual relativa (RVA) y las marcas de implementación del método o campo representado por el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `tk`  
 [in] Un token de metadatos MethodDef o FieldDef que representa el objeto de código para devolver la RVA. Si el token es un FieldDef, el campo debe ser una variable global.  
  
 `pulCodeRVA`  
 [out] Un puntero a la dirección virtual relativa del objeto de código representado por el token.  
  
 `pdwImplFlags`  
 [out] Un puntero a los marcadores de implementación para el método. Este valor es una máscara de bits desde el [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeración. El valor de `pdwImplFlags` es válido únicamente si `tk` es un token de MethodDef.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
