---
description: 'Más información acerca de: Strongnamegetblobfromimage ((función)'
title: StrongNameGetBlobFromImage (Función)
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
ms.openlocfilehash: c68d6914d47fbb711c49c1e8432cae1bf33e771f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636356"
---
# <a name="strongnamegetblobfromimage-function"></a>StrongNameGetBlobFromImage (Función)

Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: strongnamegetblobfromimage (](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pbBase`  
 de Dirección de memoria del manifiesto del ensamblado asignado.  
  
 `dwLength`  
 de Tamaño, en bytes, de la imagen en `pbBase` .  
  
 `pbBlob`  
 de Búfer que va a contener la representación binaria de la imagen.  
  
 `pcbBlob`  
 [in, out] Tamaño máximo solicitado, en bytes, de `pbBlob` . Después de la devolución, el tamaño real, en bytes, de `pbBlob` .  
  
## <a name="return-value"></a>Valor devuelto  

 `true` Cuando se complete correctamente; en caso contrario, `false` .  
  
## <a name="remarks"></a>Observaciones  

 Si la `StrongNameGetBlobFromImage` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [Método StrongNameGetBlob](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
