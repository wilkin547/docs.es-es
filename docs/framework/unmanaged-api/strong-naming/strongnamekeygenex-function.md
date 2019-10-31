---
title: StrongNameKeyGenEx (Función)
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
ms.openlocfilehash: 63ddd90f3a8090853d10f03052915d10e1503ea6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125209"
---
# <a name="strongnamekeygenex-function"></a>StrongNameKeyGenEx (Función)
Genera un nuevo par de claves pública y privada con el tamaño de clave especificado para el uso de nombres seguros.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: StrongNameKeyGenEx (](../hosting/iclrstrongname-strongnamekeygenex-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszKeyContainer`  
 de Nombre del contenedor de claves solicitado. `wszKeyContainer` debe ser una cadena no vacía o null para generar un nombre temporal.  
  
 `dwFlags`  
 de Especifica si se debe dejar registrada la clave. Se admiten los siguientes valores:  
  
- 0x00000000: se usa cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.  
  
- 0x00000001 (`SN_LEAVE_KEY`): especifica que la clave se debe dejar registrada.  
  
 `dwKeySize`  
 de Tamaño solicitado de la clave, en bits.  
  
 `ppbKeyBlob`  
 enuncia Par de claves pública y privada devuelta.  
  
 `pcbKeyBlob`  
 enuncia Tamaño, en bytes, de `ppbKeyBlob`.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` cuando se complete correctamente; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Las versiones .NET Framework 1,0 y 1,1 requieren un `dwKeySize` de 1024 bits para firmar un ensamblado con un nombre seguro. la versión 2,0 agrega compatibilidad con claves de 2048 bits.  
  
 Una vez recuperada la clave, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.  
  
 Si la función `StrongNameKeyGenEx` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameKeyGenEx (método)](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [StrongNameKeyGen (método)](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
