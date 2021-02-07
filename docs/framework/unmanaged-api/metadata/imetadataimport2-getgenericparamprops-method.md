---
description: 'Más información sobre: IMetaDataImport2:: Getgenericparamprops ((método)'
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
ms.openlocfilehash: 06b522531282b4a30cdc8ebf001c16438e8612ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688733"
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
 enuncia Posición ordinal del `Type` parámetro en el constructor o método primario.  
  
 `pdwParamFlags`  
 enuncia Un valor de la enumeración [CorGenericParamAttr (](corgenericparamattr-enumeration.md) que describe el `Type` para el parámetro genérico.  
  
 `ptOwner`  
 enuncia Un token TypeDef o MethodDef que representa el propietario del parámetro.  
  
 `reserved`  
 enuncia Reservado para extensibilidad futura.  
  
 `wzName`  
 enuncia Nombre del parámetro genérico.  
  
 `cchName`  
 de Tamaño del `wzName` búfer.  
  
 `pchName`  
 enuncia Tamaño devuelto del nombre, en caracteres anchos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
