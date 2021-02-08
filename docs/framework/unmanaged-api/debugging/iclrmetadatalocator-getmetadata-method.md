---
description: 'Más información sobre: Iclrmetadatalocator (:: GetMetadata (método)'
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
ms.openlocfilehash: 4a7e8b906b66c4295dd24800d260790526114701
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772632"
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
  
## <a name="remarks"></a>Observaciones  

 Este método lo implementa el escritor de la aplicación de depuración.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRMetadataLocator (Interfaz)](iclrmetadatalocator-interface.md)
