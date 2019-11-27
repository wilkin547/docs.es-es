---
title: IMetaDataImport::GetClassLayout (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
ms.openlocfilehash: 8360a74e9e18e5b68ecc9edd7be2e3a711cb61c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437774"
---
# <a name="imetadataimportgetclasslayout-method"></a>IMetaDataImport::GetClassLayout (Método)
Obtiene la información de diseño de la clase a la que hace referencia el token TypeDef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetClassLayout  (   
   [in]  mdTypeDef          td,   
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `td`  
 de El token de TypeDef para la clase con el diseño que se va a devolver.  
  
 `pdwPackSize`  
 enuncia Uno de los valores 1, 2, 4, 8 o 16 que representa el tamaño de paquete de la clase.  
  
 `rFieldOffset`  
 enuncia Matriz de valores de [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) .  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rFieldOffset`.  
  
 `pcFieldOffset`  
 enuncia Número de elementos devueltos en `rFieldOffset`.  
  
 `pulClassSize`  
 enuncia Tamaño en bytes de la clase representada por `td`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
