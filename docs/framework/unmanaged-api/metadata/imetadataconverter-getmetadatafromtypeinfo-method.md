---
title: IMetaDataConverter::GetMetaDataFromTypeInfo (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b87bc814179b35f594ec8fab812055ff0182c5c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145852"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a>IMetaDataConverter::GetMetaDataFromTypeInfo (Método)
Obtiene un puntero a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instancia que representa la firma de metadatos de la biblioteca de tipos al que hace referencia especificado `ITypeInfo` instancia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pITI`  
 [in] Un puntero a un `ITypeInfo` objeto que hace referencia a la biblioteca de tipos.  
  
 `ppMDI`  
 [out] Un puntero a una ubicación que recibe la dirección de la `IMetaDataImport` instancia que representa la firma de metadatos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataImport (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
