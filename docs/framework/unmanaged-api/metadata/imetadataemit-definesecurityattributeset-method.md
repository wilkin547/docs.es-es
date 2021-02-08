---
description: 'Más información acerca de: IMetaDataEmit::D método efineSecurityAttributeSet'
title: IMetaDataEmit::DefineSecurityAttributeSet (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
ms.openlocfilehash: 3512857ca23d65389b0e150bd24234d272ddd9b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784059"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a>IMetaDataEmit::DefineSecurityAttributeSet (Método)

Crea un conjunto de permisos de seguridad que se van a adjuntar al objeto al que hace referencia el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineSecurityAttributeSet (
    [in]  mdToken       tkObj,
    [in]  COR_SECATTR   rSecAttrs[],
    [in]  ULONG         cSecAttrs,
    [out] ULONG         *pulErrorAttr
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `tkObj`  
 de El token al que se adjunta la información de seguridad.  
  
 `rSecAttrs`  
 de Matriz de `COR_SECATTR` estructuras.  
  
 `cSecAttrs`  
 de Número de elementos de `rSecAttrs` .  
  
 `pulErrorAttr`  
 enuncia Si se produce un error en el método, especifica el índice `rSecAttrs` del elemento que provocó el problema.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
