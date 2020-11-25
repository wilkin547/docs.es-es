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
ms.openlocfilehash: f28ee5767997240018d182b8303e4f65be81c702
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708548"
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
 de Nombre del contenedor de claves solicitado. `wszKeyContainer` debe ser una cadena no vacía, o null para generar un nombre temporal.  
  
 `dwFlags`  
 de Especifica si se debe dejar registrada la clave. Se admiten los valores siguientes:  
  
- 0x00000000: se utiliza cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.  
  
- 0x00000001 ( `SN_LEAVE_KEY` ): especifica que la clave se debe dejar registrada.  
  
 `dwKeySize`  
 de Tamaño solicitado de la clave, en bits.  
  
 `ppbKeyBlob`  
 enuncia Par de claves pública y privada devuelta.  
  
 `pcbKeyBlob`  
 enuncia Tamaño, en bytes, de `ppbKeyBlob` .  
  
## <a name="return-value"></a>Valor devuelto  

 `true` Cuando se complete correctamente; en caso contrario, `false` .  
  
## <a name="remarks"></a>Comentarios  

 Las versiones .NET Framework 1,0 y 1,1 requieren un `dwKeySize` de 1024 bits para firmar un ensamblado con un nombre seguro; la versión 2,0 agrega admite claves de 2048 bits.  
  
 Una vez recuperada la clave, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.  
  
 Si la `StrongNameKeyGenEx` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [Método StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
