---
title: StrongNameSignatureSize (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 705771bb04088edf8276bf36432ef88ff288ba34
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751732"
---
# <a name="strongnamesignaturesize-function"></a>StrongNameSignatureSize (Función)
Devuelve el tamaño de la firma de nombre seguro. `StrongNameSignatureSize` Normalmente se usa por los compiladores para determinar cuánto espacio se reserva en el archivo al crear un ensamblado con firma retrasada.  
  
 Esta función está desusada. Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a>Parámetros  
 `pbPublicKeyBlob`  
 [in] Una estructura de tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.  
  
 `cbPublicKeyBlob`  
 [in] El tamaño, en bytes, de `pbPublicKeyBlob`.  
  
 `pcbSize`  
 [in] El número de bytes necesarios para almacenar la firma de nombre seguro.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` Cuando se finaliza correctamente; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Si el `StrongNameSignatureSize` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: StrongName.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameSignatureSize (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
