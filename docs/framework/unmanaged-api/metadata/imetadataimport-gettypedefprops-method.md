---
description: 'Más información sobre: IMetaDataImport:: Gettypedefprops ((método)'
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
ms.openlocfilehash: da5c6117f636098ed0cfeddc541979d235729d63
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799283"
---
# <a name="imetadataimportgettypedefprops-method"></a>IMetaDataImport::GetTypeDefProps (Método)

Devuelve información de metadatos para el <xref:System.Type> representado por el token de TypeDef especificado.  
  
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
 de Tamaño en caracteres anchos de `szTypeDef` .  
  
 `pchTypeDef`  
 enuncia Número de caracteres anchos devueltos en `szTypeDef` .  
  
 `pdwTypeDefFlags`  
 enuncia Puntero a cualquier marca que modifique la definición de tipo. Este valor es una máscara de máscara de la enumeración [cortypeattr (](cortypeattr-enumeration.md) .  
  
 `ptkExtends`  
 enuncia Un símbolo (token) de metadatos TypeDef o TypeRef que representa el tipo base del tipo solicitado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
