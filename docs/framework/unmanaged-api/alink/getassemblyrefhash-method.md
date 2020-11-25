---
title: GetAssemblyRefHash (Método)
ms.date: 03/30/2017
api_name:
- IALink.GetAssemblyRefHash
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetAssemblyRefHash
helpviewer_keywords:
- GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type:
- apiref
ms.openlocfilehash: af040c4a6c9b85930d2d9261f8587ba69eb204e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721483"
---
# <a name="getassemblyrefhash-method"></a>GetAssemblyRefHash (Método)

Recupera un objeto binario de hash para un ensamblado determinado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  

 `FileToken`  
 IDENTIFICADOR del ensamblado al que hará referencia el hash.  
  
 `ppvHash`  
 Recibe el BLOB hash resultante.  
  
 `pcbHash`  
 Recibe el tamaño, en bytes, del BLOB de hash.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h  
  
## <a name="see-also"></a>Consulte también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
