---
title: ICLRMetadataLocator::GetMetadata (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
ms.openlocfilehash: ad309290319396ff4e74e30d572effeffe802d1d
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859883"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a>ICLRMetadataLocator::GetMetadata (Método)
Lo llama el servicio de acceso a datos de Common Language Runtime (CLR) para recuperar los metadatos de una imagen.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `imagePath`  
 de Cadena que especifica la ruta de acceso del archivo de imagen.  
  
 `imageTimestamp`  
 de Marca de tiempo del archivo de imagen.  
  
 `imageSize`  
 de Tamaño del archivo de imagen.  
  
 `mvid`  
 de Identificador único global de la imagen.  
  
 `mdRva`  
 de La dirección virtual relativa (RVA) de los metadatos. La dirección es relativa a la dirección base de la imagen.  
  
 `flags`  
 [in] Reservado para uso futuro.  
  
 `bufferSize`  
 de Tamaño del búfer en el que se colocan los metadatos.  
  
 `buffer`  
 enuncia Búfer en el que se colocan los metadatos.  
  
 `dataSize`  
 enuncia Tamaño de los metadatos que se devuelven.  
  
## <a name="remarks"></a>Comentarios  
 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRMetadataLocator (Interfaz)](iclrmetadatalocator-interface.md)
