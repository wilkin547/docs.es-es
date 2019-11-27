---
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
ms.openlocfilehash: 0542c518b64764ad27aa00b8d595be1191059436
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437447"
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
 enuncia Puntero a las marcas de semántica asociadas. Este valor es una máscara de máscara de la enumeración [cormethodsemanticsattr (](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) .  
  
## <a name="remarks"></a>Comentarios  
 El método [IMetaDataEmit::D efineproperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) establece las marcas semánticas de un método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
