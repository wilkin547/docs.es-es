---
title: IMetaDataConverter::GetTypeLibFromMetaData (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: 79bd8901641ee587e94861c0aec85b812591ea48
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008422"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a>IMetaDataConverter::GetTypeLibFromMetaData (Método)
Obtiene un puntero a una `ITypeLib` instancia de que representa la biblioteca de tipos que tiene los nombres de biblioteca y de módulo especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `strModule`  
 de Nombre del módulo de la biblioteca de tipos.  
  
 `strTlbName`  
 de Nombre de la biblioteca de tipos.  
  
 `ppITL`  
 enuncia Puntero a una ubicación que recibe la dirección de la `ITypeLib` instancia de que representa la biblioteca de tipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataConverter (Interfaz)](imetadataconverter-interface.md)
