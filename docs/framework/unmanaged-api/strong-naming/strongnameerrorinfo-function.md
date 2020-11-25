---
title: StrongNameErrorInfo (Función)
ms.date: 03/30/2017
api_name:
- StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameErrorInfo
helpviewer_keywords:
- StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type:
- apiref
ms.openlocfilehash: 90abfcd573795ae529714e21b13f90d6e15c7dad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732273"
---
# <a name="strongnameerrorinfo-function"></a>StrongNameErrorInfo (Función)

Obtiene el último código de error generado por una de las funciones de nombres seguros.  
  
 Esta función está en desuso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StrongNameErrorInfo ();
```  
  
## <a name="return-value"></a>Valor devuelto  

 El último código de error COM establecido por una de las funciones de nombre seguro.  
  
## <a name="remarks"></a>Comentarios  

 La mayoría de los métodos de nombre seguro devuelven un simple `true` o una `false` indicación de finalización correcta. Utilice la `StrongNameErrorInfo` función para recuperar un valor HRESULT que especifica el último error generado por las funciones de nombre seguro.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
