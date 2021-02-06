---
description: 'Más información sobre: IMetaDataEmit:: Setmethodimplflags ((método)'
title: IMetaDataEmit::SetMethodImplFlags (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
ms.openlocfilehash: ea7f3122a21c8651014e60de3629db87eeaf6260
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657843"
---
# <a name="imetadataemitsetmethodimplflags-method"></a>IMetaDataEmit::SetMethodImplFlags (Método)

Establece o actualiza la firma de metadatos de la implementación del método heredado a la que hace referencia el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `md`  
 de Token para el método que se va a cambiar.  
  
 `dwImplFlags`  
 de Una combinación de los valores de la enumeración [CorMethodImpl (](cormethodimpl-enumeration.md) que especifica las características de implementación del método.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
