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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9ab908866402bd7a883114466f32921321a5ee6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799012"
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
 de Nombre del contenedor de claves solicitado. `wszKeyContainer`debe ser una cadena no vacía, o null para generar un nombre temporal.  
  
 `dwFlags`  
 de Especifica si se debe dejar registrada la clave. Se admiten los siguientes valores:  
  
- 0x00000000: se utiliza `wszKeyContainer` cuando es null para generar un nombre de contenedor de claves temporal.  
  
- 0x00000001 (`SN_LEAVE_KEY`): especifica que la clave se debe dejar registrada.  
  
 `dwKeySize`  
 de Tamaño solicitado de la clave, en bits.  
  
 `ppbKeyBlob`  
 enuncia Par de claves pública y privada devuelta.  
  
 `pcbKeyBlob`  
 enuncia Tamaño, en bytes, de `ppbKeyBlob`.  
  
## <a name="return-value"></a>Valor devuelto  
 `true`Cuando se complete correctamente; en caso `false`contrario,.  
  
## <a name="remarks"></a>Comentarios  
 Las versiones .NET Framework 1,0 y 1,1 requieren un `dwKeySize` de 1024 bits para firmar un ensamblado con un nombre seguro; la versión 2,0 agrega admite claves de 2048 bits.  
  
 Una vez recuperada la clave, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.  
  
 Si la `StrongNameKeyGenEx` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: StrongName. h  
  
 **Biblioteca** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameKeyGenEx (método)](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [StrongNameKeyGen (método)](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
