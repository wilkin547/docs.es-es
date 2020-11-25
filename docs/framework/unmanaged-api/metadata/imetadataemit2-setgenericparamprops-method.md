---
title: IMetaDataEmit2::SetGenericParamProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
ms.openlocfilehash: 8858e692d66f7b34a66334bd4e8b906dd12962ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701996"
---
# <a name="imetadataemit2setgenericparamprops-method"></a>IMetaDataEmit2::SetGenericParamProps (Método)

Establece los valores de propiedad para la definición de parámetro genérico a la que hace referencia el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `gp`  
 de Token de la definición de parámetro genérico para el que se van a establecer valores.  
  
 `dwParamFlags`  
 de Un valor de la enumeración [CorGenericParamAttr (](corgenericparamattr-enumeration.md) que describe el tipo para el parámetro genérico.  
  
 `szName`  
 [in] Opcional. Nombre del parámetro para el que se van a establecer valores.  
  
 `reserved`  
 [in] Reservado para extensibilidad futura.  
  
 `rtkConstraints`  
 [in] Opcional. Matriz terminada en cero de restricciones de tipo. Los miembros de la matriz deben ser un `mdTypeDef` `mdTypeRef` `mdTypeSpec` token de metadatos, o.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
