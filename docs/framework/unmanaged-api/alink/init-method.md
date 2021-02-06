---
description: 'Más información sobre: método init'
title: Init (Método)
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
ms.openlocfilehash: 531e05a09cbecbfb67c8c004d1e4ba1deb7e59a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662564"
---
# <a name="init-method"></a>Init (Método)

Prepara objetos que implementan la [interfaz ialink (](ialink-interface.md) para su uso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  

 `pDispenser`  
 Puntero de la [interfaz IMetaDataDispenserEx](../metadata/imetadatadispenserex-interface.md) al dispensador de metadatos.  
  
 `pErrorHandler`  
 Puntero de [interfaz imetadataerror (](../metadata/imetadataerror-interface.md) a una interfaz de control de errores opcional.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
