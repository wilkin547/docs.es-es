---
title: IMetaDataImport::GetClassLayout (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
ms.openlocfilehash: 5a442d8d0916b0e86f25c03507de66fc999f2159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711265"
---
# <a name="imetadataimportgetclasslayout-method"></a>IMetaDataImport::GetClassLayout (Método)

Obtiene la información de diseño de la clase a la que hace referencia el token TypeDef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetClassLayout  (
   [in]  mdTypeDef          td,
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `td`  
 de El token de TypeDef para la clase con el diseño que se va a devolver.  
  
 `pdwPackSize`  
 enuncia Uno de los valores 1, 2, 4, 8 o 16 que representa el tamaño de paquete de la clase.  
  
 `rFieldOffset`  
 enuncia Matriz de valores de [COR_FIELD_OFFSET](cor-field-offset-structure.md) .  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rFieldOffset`.  
  
 `pcFieldOffset`  
 enuncia Número de elementos devueltos en `rFieldOffset` .  
  
 `pulClassSize`  
 enuncia Tamaño en bytes de la clase representada por `td` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
