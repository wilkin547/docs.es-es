---
description: 'Más información acerca de: Strongnametokenfromassemblyex ((función)'
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
ms.openlocfilehash: 4ca08c8cfa90415723fc2632e32aa8f45c334db3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636290"
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

 `true` Cuando se complete correctamente; en caso contrario, `false` .  
  
## <a name="remarks"></a>Observaciones  

 Un token de nombre seguro es la forma abreviada de una clave pública. El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado. El token es una parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.  
  
 Una vez recuperada la clave y creado el token, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.  
  
 Si la `StrongNameTokenFromAssemblyEx` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en mscoree.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [Método StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
