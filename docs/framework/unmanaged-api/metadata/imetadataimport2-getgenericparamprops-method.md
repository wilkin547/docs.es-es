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
ms.openlocfilehash: a8c5dd263401002deaee3d21f1e41b41a29faec2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427297"
---
# <a name="imetadataimport2getgenericparamprops-method"></a>IMetaDataImport2::GetGenericParamProps (Método)
Obtiene los metadatos asociados al parámetro genérico representado por el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de El token que representa el parámetro genérico para el que se van a devolver los metadatos.  
  
 `pulParamSeq`  
 enuncia Posición ordinal del parámetro `Type` en el constructor o método primario.  
  
 `pdwParamFlags`  
 enuncia Un valor de la enumeración [CorGenericParamAttr (](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) que describe el `Type` para el parámetro genérico.  
  
 `ptOwner`  
 enuncia Un token TypeDef o MethodDef que representa el propietario del parámetro.  
  
 `reserved`  
 enuncia Reservado para extensibilidad futura.  
  
 `wzName`  
 enuncia Nombre del parámetro genérico.  
  
 `cchName`  
 de Tamaño del búfer de `wzName`.  
  
 `pchName`  
 enuncia Tamaño devuelto del nombre, en caracteres anchos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
