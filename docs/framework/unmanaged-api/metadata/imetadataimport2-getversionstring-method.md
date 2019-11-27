---
title: IMetaDataImport2::GetVersionString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
ms.openlocfilehash: 0c9f667edf30feb23e1cdaa28950503283fce42e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445225"
---
# <a name="imetadataimport2getversionstring-method"></a>IMetaDataImport2::GetVersionString (Método)
Obtiene el número de versión del motor en tiempo de ejecución que se usó para compilar el ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzBuf`  
 enuncia Matriz para almacenar la cadena que especifica la versión.  
  
 `ccBufSize`  
 de Tamaño, en caracteres anchos, de la matriz de `pwzBuf`.  
  
 `pccBufSize`  
 enuncia El número de caracteres anchos, incluido un terminador nulo, devuelto en la matriz `pwzBuf`.  
  
## <a name="remarks"></a>Comentarios  
 El método `GetVersionString` obtiene la versión integrada del ámbito de metadatos actual. Si el ámbito no se ha guardado nunca, no tendrá una versión integrada y se devolverá una cadena vacía.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
