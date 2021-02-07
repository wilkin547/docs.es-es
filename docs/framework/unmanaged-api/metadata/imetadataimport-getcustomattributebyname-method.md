---
description: 'Más información sobre: IMetaDataImport:: Getcustomattributebyname ((método)'
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
ms.openlocfilehash: 1a9ca5f7fe13243c01c5dbcb9f49955e9ce05c26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745494"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a>IMetaDataImport::GetCustomAttributeByName (Método)

Obtiene el atributo personalizado, dado su nombre y propietario.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `tkObj`  
 de Un token de metadatos que representa el objeto que posee el atributo personalizado.  
  
 `szName`  
 de Nombre del atributo personalizado.  
  
 `ppData`  
 enuncia Puntero a una matriz de datos que es el valor del atributo personalizado.  
  
 `pcbData`  
 enuncia Tamaño en bytes de los datos devueltos en * `ppData` .  
  
## <a name="remarks"></a>Observaciones  

 Es legal definir varios atributos personalizados para el mismo propietario. incluso pueden tener el mismo nombre. Sin embargo, `GetCustomAttributeByName` devuelve solo una instancia. ( `GetCustomAttributeByName` devuelve la primera instancia que encuentra). Para buscar todas las instancias de un atributo personalizado, llame al método [IMetaDataImport:: enumcustomattributes (](imetadataimport-enumcustomattributes-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
