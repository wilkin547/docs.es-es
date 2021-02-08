---
description: 'Más información sobre: IMetaDataImport:: GetMethodProps ((método)'
title: IMetaDataImport::GetMethodProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
ms.openlocfilehash: 5fb344d72378a806e0e71820b55a90998e497916
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783889"
---
# <a name="imetadataimportgetmethodprops-method"></a>IMetaDataImport::GetMethodProps (Método)

Obtiene los metadatos asociados al método al que hace referencia el token de MethodDef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="parameters"></a>Parámetros  

 `mb`  
 de Token de MethodDef que representa el método para el que se van a devolver los metadatos.  
  
 `pClass`  
 enuncia Un puntero a un token de TypeDef que representa el tipo que implementa el método.  
  
 `szMethod`  
 enuncia Puntero a un búfer que tiene el nombre del método.  
  
 `cchMethod`  
 de Tamaño solicitado de `szMethod` .  
  
 `pchMethod`  
 enuncia Puntero al tamaño en caracteres anchos de `szMethod` , o en el caso del truncamiento, el número real de caracteres anchos en el nombre del método.  
  
 `pdwAttr`  
 enuncia Puntero a cualquier marca asociada al método.  
  
 `ppvSigBlob`  
 enuncia Puntero a la firma de metadatos binarios del método.  
  
 `pcbSigBlob`  
 enuncia Puntero al tamaño en bytes de `ppvSigBlob` .  
  
 `pulCodeRVA`  
 enuncia Puntero a la dirección virtual relativa del método.  
  
 `pdwImplFlags`  
 enuncia Un puntero a cualquier marcador de implementación para el método.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
