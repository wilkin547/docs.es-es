---
description: 'Más información sobre: IMetaDataAssemblyImport:: Enumexportedtypes ((método)'
title: IMetaDataAssemblyImport::EnumExportedTypes (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: ecddcbd87586f5f61c57f8c04ea3bd68dc652839
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678034"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a>IMetaDataAssemblyImport::EnumExportedTypes (Método)

Enumera los tipos exportados a los que se hace referencia en el manifiesto del ensamblado en el ámbito de metadatos actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `phEnum`  
 [in, out] Puntero al enumerador. Debe ser un valor NULL cuando `EnumExportedTypes` se llama al método por primera vez.  
  
 `rExportedTypes`  
 enuncia Enumeración de los `mdExportedType` tokens de metadatos.  
  
 `cMax`  
 de Número máximo de `mdExportedType` tokens que se pueden colocar en la `rExportedTypes` matriz.  
  
 `pcTokens`  
 enuncia Número de `mdExportedType` tokens realmente colocados en `rExportedTypes` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumExportedTypes` se devolvió correctamente.|  
|`S_FALSE`|No hay tokens que enumerar. En este caso, `pcTokens` se establece en cero.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
