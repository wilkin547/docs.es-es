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
ms.openlocfilehash: 3e62b1177c0161883ad03086723cc43b71292df5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702568"
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
 de Tamaño, en caracteres anchos, de la `pwzBuf` matriz.  
  
 `pccBufSize`  
 enuncia El número de caracteres anchos, incluido un terminador nulo, devuelto en la `pwzBuf` matriz.  
  
## <a name="remarks"></a>Comentarios  

 El `GetVersionString` método obtiene la versión integrada del ámbito de metadatos actual. Si el ámbito no se ha guardado nunca, no tendrá una versión integrada y se devolverá una cadena vacía.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
