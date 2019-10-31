---
title: StrongNameTokenFromAssemblyEx (Función)
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
ms.openlocfilehash: 8b7866b92be3195b0a767a823a0d7fb1c0aa4918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104247"
---
# <a name="strongnametokenfromassemblyex-function"></a>StrongNameTokenFromAssemblyEx (Función)
Crea un token de nombre seguro a partir del archivo de ensamblado especificado y devuelve la clave pública que representa el token.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: strongnametokenfromassemblyex (](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 de La ruta de acceso al archivo portable ejecutable (PE) para el ensamblado.  
  
 `ppbStrongNameToken`  
 enuncia El token de nombre seguro devuelto.  
  
 `pcbStrongNameToken`  
 enuncia Tamaño, en bytes, del token de nombre seguro.  
  
 `ppbPublicKeyBlob`  
 enuncia La clave pública devuelta.  
  
 `pcbPublicKeyBlob`  
 enuncia Tamaño, en bytes, de la clave pública.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` cuando se complete correctamente; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Un token de nombre seguro es la forma abreviada de una clave pública. El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado. El token es una parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.  
  
 Una vez recuperada la clave y creado el token, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.  
  
 Si la función `StrongNameTokenFromAssemblyEx` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como recurso en Mscoree. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameTokenFromAssemblyEx (método)](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [StrongNameTokenFromAssembly (método)](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
