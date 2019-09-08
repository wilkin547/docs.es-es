---
title: StrongNameTokenFromAssembly (Función)
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71058a1ff82335b2a341904805d06738e662c296
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798862"
---
# <a name="strongnametokenfromassembly-function"></a>StrongNameTokenFromAssembly (Función)
Crea un token de nombre seguro desde el archivo de ensamblado especificado.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: StrongNameTokenFromAssembly (](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 de La ruta de acceso al archivo portable ejecutable (PE) para el ensamblado.  
  
 `ppbStrongNameToken`  
 enuncia El token de nombre seguro devuelto.  
  
 `pcbStrongNameToken`  
 enuncia Tamaño, en bytes, del token de nombre seguro.  
  
## <a name="return-value"></a>Valor devuelto  
 `true`Cuando se complete correctamente; en caso `false`contrario,.  
  
## <a name="remarks"></a>Comentarios  
 Un token de nombre seguro es la forma abreviada de una clave pública. El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado. El token es una parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.  
  
 Una vez creado el token, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.  
  
 Si la `StrongNameTokenFromAssembly` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: StrongName. h  
  
 **Biblioteca** Se incluye como recurso en Mscoree. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameTokenFromAssembly (método)](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [StrongNameTokenFromAssemblyEx (método)](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
