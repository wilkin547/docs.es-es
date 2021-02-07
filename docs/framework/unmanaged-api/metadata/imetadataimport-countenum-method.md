---
description: 'Más información sobre: IMetaDataImport:: Countenum ((método)'
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
ms.openlocfilehash: c579ef7ce440e3552ab28572fc6c96ad12d66400
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677696"
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
  
## <a name="remarks"></a>Observaciones  

 El identificador especificado por `hEnum` se obtiene a partir de una llamada de `Enum` *nombre* anterior (por ejemplo, [IMetaDataImport:: enumtypedefs (](imetadataimport-enumtypedefs-method.md)).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
