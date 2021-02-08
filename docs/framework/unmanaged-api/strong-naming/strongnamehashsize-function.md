---
description: 'Más información acerca de: Strongnamehashsize ((función)'
title: StrongNameHashSize (Función)
ms.date: 03/30/2017
api_name:
- StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameHashSize
helpviewer_keywords:
- StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type:
- apiref
ms.openlocfilehash: 3e6700bfce3ba480814f3837011c5f8f7107bbd5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781251"
---
# <a name="strongnamehashsize-function"></a>StrongNameHashSize (Función)

Obtiene el tamaño de búfer necesario para un hash mediante el algoritmo hash especificado.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: strongnamehashsize (](../hosting/iclrstrongname-strongnamehashsize-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ulHashAlg`  
 de Algoritmo hash que se usa para calcular el tamaño del búfer.  
  
 `pcbSize`  
 enuncia Tamaño de búfer devuelto, en bytes.  
  
## <a name="return-value"></a>Valor devuelto  

 `true` Cuando se complete correctamente; en caso contrario, `false` .  
  
## <a name="remarks"></a>Observaciones  

 Si la `StrongNameHashSize` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
