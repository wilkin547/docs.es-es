---
title: IMetaDataImport::GetTypeDefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
ms.openlocfilehash: c9ac624e17223def206e86fd92ee4fd2de7f6082
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436749"
---
# <a name="imetadataimportgettypedefprops-method"></a>IMetaDataImport::GetTypeDefProps (Método)
Devuelve información de metadatos para la <xref:System.Type> representada por el token de TypeDef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `td`  
 de El token de TypeDef que representa el tipo para el que se van a devolver los metadatos.  
  
 `szTypeDef`  
 enuncia Búfer que contiene el nombre del tipo.  
  
 `cchTypeDef`  
 de Tamaño en caracteres anchos de `szTypeDef`.  
  
 `pchTypeDef`  
 enuncia Número de caracteres anchos devueltos en `szTypeDef`.  
  
 `pdwTypeDefFlags`  
 enuncia Puntero a cualquier marca que modifique la definición de tipo. Este valor es una máscara de máscara de la enumeración [cortypeattr (](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) .  
  
 `ptkExtends`  
 enuncia Un símbolo (token) de metadatos TypeDef o TypeRef que representa el tipo base del tipo solicitado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
