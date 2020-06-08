---
title: IMetaDataImport::GetNameFromToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
ms.openlocfilehash: 6d62739148280c7333cf7cdb6002b59a145496e3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503567"
---
# <a name="imetadataimportgetnamefromtoken-method"></a>IMetaDataImport::GetNameFromToken (Método)
Obtiene el nombre en UTF-8 del objeto al que hace referencia el token de metadatos especificado. Este método está obsoleto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `tk`  
 de Token que representa el objeto para el que se va a devolver el nombre.  
  
 `pszUtf8NamePtr`  
 enuncia Puntero al nombre del objeto UTF-8 en el montón.  
  
## <a name="remarks"></a>Comentarios  
 `GetNameFromToken` está obsoleto. Como alternativa, llame a un método para obtener las propiedades del tipo determinado de token requerido, como `GetFieldProps` para un campo o `GetMethodProps` para un método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** 1,0  
  
## <a name="see-also"></a>Consulte también:

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
