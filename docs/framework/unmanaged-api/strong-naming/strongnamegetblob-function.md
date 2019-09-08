---
title: StrongNameGetBlob (Función)
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d5b3d1d39b5d4c5b7d4db073b3ffaf1c6b88373
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799101"
---
# <a name="strongnamegetblob-function"></a>StrongNameGetBlob (Función)
Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: strongnamegetblob (](../hosting/iclrstrongname-strongnamegetblob-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 de Ruta de acceso válida al archivo ejecutable que se va a cargar.  
  
 `pbBlob`  
 de Búfer en el que se va a cargar el archivo ejecutable.  
  
 `pcbBlob`  
 [in, out] Tamaño máximo solicitado, en bytes, de `pbBlob`. Después de la devolución, el tamaño real, en bytes `pbBlob`, de.  
  
## <a name="return-value"></a>Valor devuelto  
 `true`Cuando se complete correctamente; en caso `false`contrario,.  
  
## <a name="remarks"></a>Comentarios  
 Si la `StrongNameGetBlob` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: StrongName. h  
  
 **Biblioteca** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameGetBlob (método)](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [StrongNameGetBlobFromImage (método)](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
