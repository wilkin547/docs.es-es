---
title: IMetaDataImport::GetParamForMethodIndex (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamForMethodIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7455d87caff86c57409f4bb016ec73c365a3d35d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487127"
---
# <a name="imetadataimportgetparamformethodindex-method"></a>IMetaDataImport::GetParamForMethodIndex (Método)
Obtiene el token que representa un parámetro especificado del método representado por el token de MethodDef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `md`  
 [in] Un token que representa el método para devolver el token de parámetro para.  
  
 `ulParamSeq`  
 [in] La posición ordinal en la lista de parámetros que se produce el parámetro solicitado. Los parámetros se numeran a partir de uno, con el valor devuelto del método en la posición cero.  
  
 `ppd`  
 [out] Un puntero a un token de ParamDef que representa el parámetro solicitado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
