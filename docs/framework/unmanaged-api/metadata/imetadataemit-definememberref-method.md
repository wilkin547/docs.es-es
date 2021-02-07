---
description: 'Más información acerca de: IMetaDataEmit::D método efineMemberRef'
title: IMetaDataEmit::DefineMemberRef (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
ms.openlocfilehash: 1d88294cea14369c8a8f16b6048f96472fbb9502
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753424"
---
# <a name="imetadataemitdefinememberref-method"></a>IMetaDataEmit::DefineMemberRef (Método)

Define una referencia a un miembro de un módulo fuera del ámbito actual y obtiene un token para esa definición de referencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `tkImport`  
 de Token de la clase o interfaz del miembro de destino, si el miembro no es global; Si el miembro es global, el `mdModuleRef` token del otro archivo.  
  
 `szName`  
 de Nombre del miembro de destino.  
  
 `pvSigBlob`  
 de Firma del miembro de destino.  
  
 `cbSigBlob`  
 de Recuento de bytes de `pvSigBlob` .  
  
 `pmr`  
 enuncia El `mdMemberRef` token asignado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
