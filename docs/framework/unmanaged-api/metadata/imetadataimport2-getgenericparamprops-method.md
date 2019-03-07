---
title: IMetaDataImport2::GetGenericParamProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fc2d64a97d02d6f6036646634113cf485119eba7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490364"
---
# <a name="imetadataimport2getgenericparamprops-method"></a>IMetaDataImport2::GetGenericParamProps (Método)
Obtiene los metadatos asociados con el parámetro genérico representado por el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `gp`  
 [in] El token que representa el parámetro genérico para el que se va a devolver los metadatos.  
  
 `pulParamSeq`  
 [out] La posición ordinal de la `Type` parámetro en el método o constructor principal.  
  
 `pdwParamFlags`  
 [out] Un valor de la [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeración que describe el `Type` para el parámetro genérico.  
  
 `ptOwner`  
 [out] Un token de TypeDef o MethodDef que representa el propietario del parámetro.  
  
 `reserved`  
 [out] Reservado para extensibilidad futura.  
  
 `wzName`  
 [out] El nombre del parámetro genérico.  
  
 `cchName`  
 [in] El tamaño de la `wzName` búfer.  
  
 `pchName`  
 [out] El tamaño devuelto del nombre, en caracteres anchos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
