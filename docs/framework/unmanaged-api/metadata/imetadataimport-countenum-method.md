---
title: IMetaDataImport::CountEnum (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
ms.openlocfilehash: 4521a3f15ec358a4d786a4533efb6b99d0e1c1cc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492387"
---
# <a name="imetadataimportcountenum-method"></a>IMetaDataImport::CountEnum (Método)
Obtiene el número de elementos de la enumeración recuperados por el enumerador especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `hEnum`  
 de Identificador del enumerador.  
  
 `pulCount`  
 enuncia Número de elementos enumerados.  
  
## <a name="remarks"></a>Comentarios  
 El identificador especificado por `hEnum` se obtiene a partir de una llamada de `Enum` *nombre* anterior (por ejemplo, [IMetaDataImport:: enumtypedefs (](imetadataimport-enumtypedefs-method.md)).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
