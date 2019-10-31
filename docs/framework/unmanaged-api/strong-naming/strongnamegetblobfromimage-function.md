---
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
ms.openlocfilehash: 41226cd909900bd2da7bdcf9b9a49567d3042b01
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73094886"
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
 de Tamaño, en bytes, de la imagen en `pbBase`.  
  
 `pbBlob`  
 de Búfer que va a contener la representación binaria de la imagen.  
  
 `pcbBlob`  
 [in, out] Tamaño máximo solicitado, en bytes, de `pbBlob`. Cuando se devuelve, el tamaño real, en bytes, de `pbBlob`.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` cuando se complete correctamente; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Si la función `StrongNameGetBlobFromImage` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameGetBlobFromImage (método)](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [StrongNameGetBlob (método)](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
