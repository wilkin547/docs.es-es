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
ms.openlocfilehash: a19d875b8fb81f2af3821e69452f0f0ed591cd22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176895"
---
# <a name="strongnamesignaturesize-function"></a>StrongNameSignatureSize (Función)
Devuelve el tamaño de la firma de nombre seguro. `StrongNameSignatureSize`Normalmente, los compiladores se usan para determinar cuánto espacio se debe reservar en el archivo al crear un ensamblado firmado con retraso.  
  
 Esta función ha quedado en desuso. Utilice el [método ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) en su lugar.  
  
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
 [en] Estructura de tipo [PublicKeyBlob](publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.  
  
 `cbPublicKeyBlob`  
 [en] El tamaño, en `pbPublicKeyBlob`bytes, de .  
  
 `pcbSize`  
 [en] El número de bytes necesarios para almacenar la firma de nombre seguro.  
  
## <a name="return-value"></a>Valor devuelto  
 `true`una finalización exitosa; de `false`lo contrario, .  
  
## <a name="remarks"></a>Observaciones  
 Si `StrongNameSignatureSize` la función no se completa correctamente, llame a la [StrongNameErrorInfo](strongnameerrorinfo-function.md) función para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
