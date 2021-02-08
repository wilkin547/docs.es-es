---
description: 'Más información sobre: IMetaDataImport:: Getrva ((método)'
title: IMetaDataImport::GetRVA (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: 8d6439bcad50a6311e7bb1408f4c86144a5026ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789169"
---
# <a name="imetadataimportgetrva-method"></a>IMetaDataImport::GetRVA (Método)

Obtiene la dirección virtual relativa (RVA) y las marcas de implementación del método o campo representado por el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `tk`  
 de Símbolo (token) de metadatos de MethodDef o FieldDef que representa el objeto de código para el que se va a devolver la RVA. Si el token es FieldDef, el campo debe ser una variable global.  
  
 `pulCodeRVA`  
 enuncia Un puntero a la dirección virtual relativa del objeto de código representado por el token.  
  
 `pdwImplFlags`  
 enuncia Puntero a las marcas de implementación para el método. Este valor es una máscara de máscara de la enumeración [CorMethodImpl (](cormethodimpl-enumeration.md) . El valor de `pdwImplFlags` solo es válido si `tk` es un token de MethodDef.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
