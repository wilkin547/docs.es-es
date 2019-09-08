---
title: StrongNameFreeBuffer (Función)
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639664c6ce5714b554f30bff2569a12bf48d1671
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799123"
---
# <a name="strongnamefreebuffer-function"></a>StrongNameFreeBuffer (Función)
Libera la memoria asignada mediante una llamada anterior a una función de nombre seguro como [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).  
  
 Esta función está en desuso. Use en su lugar el método [ICLRStrongName:: StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbMemory`  
 de Puntero a la memoria que se va a liberar.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: StrongName. h  
  
 **Biblioteca** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameFreeBuffer (método)](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
