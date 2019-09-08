---
title: StrongNameSignatureVerificationFromImage (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c22339b7d48e89f99d1500cfdda53f00f1234b80
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799070"
---
# <a name="strongnamesignatureverificationfromimage-function"></a>StrongNameSignatureVerificationFromImage (Función)
Comprueba si un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: StrongNameVerificationFromImage](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbBase`  
 de Dirección virtual relativa del manifiesto del ensamblado asignado.  
  
 `dwLength`  
 de Tamaño, en bytes, de la imagen asignada.  
  
 `dwInFlags`  
 de Marcas que influyen en el comportamiento de la comprobación. Se admiten los siguientes valores:  
  
- `SN_INFLAG_FORCE_VER`(0x00000001): fuerza la comprobación aunque sea necesario invalidar la configuración del registro.  
  
- `SN_INFLAG_INSTALL`(0x00000002): especifica que esta es la primera comprobación realizada en esta imagen.  
  
- `SN_INFLAG_ADMIN_ACCESS`(0x00000004): especifica que la memoria caché permitirá el acceso solo a los usuarios que tengan privilegios administrativos.  
  
- `SN_INFLAG_USER_ACCESS`(0x00000008): especifica que el ensamblado será accesible únicamente para el usuario actual.  
  
- `SN_INFLAG_ALL_ACCESS`(0x00000010): especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.  
  
- `SN_INFLAG_RUNTIME`(0x80000000): reservado para la depuración interna.  
  
 `pdwOutFlags`  
 enuncia Marca para la información de salida adicional. Se admite el siguiente valor:  
  
- `SN_OUTFLAG_WAS_VERIFIED`(0x00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.  
  
## <a name="return-value"></a>Valor devuelto  
 `true`Cuando se complete correctamente; en caso `false`contrario,.  
  
## <a name="remarks"></a>Comentarios  
 Si la `StrongNameSignatureVerificationFromImage` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: StrongName. h  
  
 **Biblioteca** Se incluye como recurso en Mscoree. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameSignatureVerificationFromImage (método)](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
