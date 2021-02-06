---
description: 'Más información acerca de: Strongnamekeygen ((función)'
title: StrongNameKeyGen (Función)
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
ms.openlocfilehash: c5f4cfcfa9030ae856acf5fd59ab34a2b8338670
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636275"
---
# <a name="strongnamekeygen-function"></a>StrongNameKeyGen (Función)

Crea un par de claves pública y privada para su uso en nombres seguros.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: strongnamekeygen (](../hosting/iclrstrongname-strongnamekeygen-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
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
  
 `ppbKeyBlob`  
 enuncia Par de claves pública y privada devuelta.  
  
 `pcbKeyBlob`  
 enuncia Tamaño, en bytes, de `ppbKeyBlob` .  
  
## <a name="return-value"></a>Valor devuelto  

 `true` Cuando se complete correctamente; en caso contrario, `false` .  
  
## <a name="remarks"></a>Observaciones  

 La `StrongNameKeyGen` función crea una clave de 1024 bits. Una vez recuperada la clave, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.  
  
 Si la `StrongNameKeyGen` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [Método StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
