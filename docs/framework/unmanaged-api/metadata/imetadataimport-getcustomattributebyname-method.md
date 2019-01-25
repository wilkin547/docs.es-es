---
title: IMetaDataImport::GetCustomAttributeByName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68cac76a83164e24c0810c9d19fa845c8580b1d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637255"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a>IMetaDataImport::GetCustomAttributeByName (Método)
Obtiene el atributo personalizado, dado su nombre y propietario.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `tkObj`  
 [in] Un token de metadatos que representa el objeto que posee el atributo personalizado.  
  
 `szName`  
 [in] El nombre del atributo personalizado.  
  
 `ppData`  
 [out] Un puntero a una matriz de datos que es el valor del atributo personalizado.  
  
 `pcbData`  
 [out] El tamaño en bytes de los datos devueltos en *`ppData`.  
  
## <a name="remarks"></a>Comentarios  
 Es válido para definir varios atributos personalizados para el mismo propietario; incluso es posible que tienen el mismo nombre. Sin embargo, `GetCustomAttributeByName` devuelve solo una instancia. (`GetCustomAttributeByName` devuelve la primera instancia que encuentra.) Para encontrar todas las instancias de un atributo personalizado, llame a la [EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
