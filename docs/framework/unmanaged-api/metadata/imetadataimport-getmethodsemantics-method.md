---
description: 'Más información sobre: IMetaDataImport:: Getmethodsemantics ((método)'
title: IMetaDataImport::GetMethodSemantics (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: 2b17e2ffaeef3a451850ce2cc9c4861d68df3a81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783864"
---
# <a name="imetadataimportgetmethodsemantics-method"></a>IMetaDataImport::GetMethodSemantics (Método)

Obtiene las marcas que indican la relación entre el método al que hace referencia el token de MethodDef especificado y la propiedad emparejada y el evento a los que hace referencia el token de EventProp especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `mb`  
 de Token de MethodDef que representa el método para el que se va a obtener la información de la función semántica.  
  
 `tkEventProp`  
 de Token que representa la propiedad emparejada y el evento para los que se va a obtener el rol del método.  
  
 `pdwSemanticsFlags`  
 enuncia Puntero a las marcas de semántica asociadas. Este valor es una máscara de máscara de la enumeración [cormethodsemanticsattr (](cormethodsemanticsattr-enumeration.md) .  
  
## <a name="remarks"></a>Observaciones  

 El método [IMetaDataEmit::D efineproperty](imetadataemit-defineproperty-method.md) establece las marcas semánticas de un método.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
