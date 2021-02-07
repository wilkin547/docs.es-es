---
description: 'Más información acerca de: Strongnamesignaturesize ((función)'
title: StrongNameSignatureSize (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
ms.openlocfilehash: b3f22a6a4d5455af4dd17cb75edfd18befed7de3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670533"
---
# <a name="strongnamesignaturesize-function"></a>StrongNameSignatureSize (Función)

Devuelve el tamaño de la firma de nombre seguro. `StrongNameSignatureSize` los compiladores utilizan normalmente para determinar la cantidad de espacio que se reserva en el archivo al crear un ensamblado con firma retrasada.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: strongnamesignaturesize (](../hosting/iclrstrongname-strongnamesignaturesize-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a>Parámetros  

 `pbPublicKeyBlob`  
 de Estructura de tipo [PublicKeyBlob](publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.  
  
 `cbPublicKeyBlob`  
 de Tamaño, en bytes, de `pbPublicKeyBlob` .  
  
 `pcbSize`  
 de Número de bytes necesarios para almacenar la firma de nombre seguro.  
  
## <a name="return-value"></a>Valor devuelto  

 `true` Cuando se complete correctamente; en caso contrario, `false` .  
  
## <a name="remarks"></a>Observaciones  

 Si la `StrongNameSignatureSize` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
