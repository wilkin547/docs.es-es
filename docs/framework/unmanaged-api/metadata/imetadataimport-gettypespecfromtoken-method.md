---
title: IMetaDataImport::GetTypeSpecFromToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeSpecFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53d0f3bd991d502e4ddcad7df1e24d18af367e7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54598399"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a>IMetaDataImport::GetTypeSpecFromToken (Método)
Obtiene la firma de metadatos binaria de la especificación de tipo representada por el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `typespec`  
 [in] El token de TypeSpec asociado con la firma de metadatos solicitada.  
  
 `ppvSig`  
 [out] Un puntero a la firma de metadatos binaria.  
  
 `pcbSig`  
 [out] El tamaño, en bytes, de la firma de metadatos.  
  
## <a name="return-value"></a>Valor devuelto  
 Un HRESULT que indica éxito o error. Errores se pueden probar con la macro FAILED.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
