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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a01b4203145f6ffee4e3a11a3526f0b83e3dc741
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042528"
---
# <a name="imetadataimport2getversionstring-method"></a>IMetaDataImport2::GetVersionString (Método)
Obtiene el número de versión del runtime que se usó para generar el ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzBuf`  
 [out] Una matriz para almacenar la cadena que especifica la versión.  
  
 `ccBufSize`  
 [in] El tamaño, en caracteres anchos, de la `pwzBuf` matriz.  
  
 `pccBufSize`  
 [out] Devuelve el número de caracteres anchos, incluido un terminador nulo, en el `pwzBuf` matriz.  
  
## <a name="remarks"></a>Comentarios  
 El `GetVersionString` método obtiene la versión integrada para el ámbito de metadatos actual. Si el ámbito no se ha guardado nunca, no tendrá de versión y se devolverá una cadena vacía.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
