---
description: 'Más información sobre: IMetaDataAssemblyImport:: EnumAssemblyRefs ((método)'
title: IMetaDataAssemblyImport::EnumAssemblyRefs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
ms.openlocfilehash: fc1d74d79edc21c6d3d13c80510440333d083801
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671066"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a>IMetaDataAssemblyImport::EnumAssemblyRefs (Método)

Enumera las `mdAssemblyRef` instancias de definidas en el manifiesto del ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `phEnum`  
 [in, out] Puntero al enumerador. Debe ser un valor NULL cuando `EnumAssemblyRefs` se llama al método por primera vez.  
  
 `rAssemblyRefs`  
 enuncia Enumeración de los `mdAssemblyRef` tokens de metadatos.  
  
 `cMax`  
 de Número máximo de tokens que se pueden colocar en la `rAssemblyRefs` matriz.  
  
 `pcTokens`  
 enuncia Número de tokens realmente colocados en `rAssemblyRefs` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumAssemblyRefs` se devolvió correctamente.|  
|`S_FALSE`|No hay tokens que enumerar. En este caso, `pcTokens` se establece en cero.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
