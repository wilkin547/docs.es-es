---
title: "IMetaDataImport::GetMethodProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMethodProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e4e0ae7dfed4b13ea83e16d6380443c9d1b72b06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmethodprops-method"></a>IMetaDataImport::GetMethodProps (Método)
Obtiene los metadatos asociados al método al que hace referencia el token de MethodDef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `mb`  
 [in] El token de MethodDef que representa el método para devolver los metadatos.  
  
 `pClass`  
 [out] Un puntero a un token de TypeDef que representa el tipo que implementa el método.  
  
 `szMethod`  
 [out] Un puntero a un búfer que contiene el nombre del método.  
  
 `cchMethod`  
 [in] El tamaño solicitado del `szMethod`.  
  
 `pchMethod`  
 [out] Un puntero al tamaño en caracteres anchos de `szMethod`, o en el caso de truncamiento, el número real de caracteres anchos en el nombre del método.  
  
 `pdwAttr`  
 [out] Un puntero a cualquier indicador asociado al método.  
  
 `ppvSigBlob`  
 [out] Un puntero a la firma de metadatos binaria del método.  
  
 `pcbSigBlob`  
 [out] Un puntero al tamaño en bytes de `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Un puntero a la dirección virtual relativa del método.  
  
 `pdwImplFlags`  
 [out] Un puntero a los marcadores de implementación para el método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
