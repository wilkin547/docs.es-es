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
ms.openlocfilehash: dd83fc6a7f553b54cc2acd5e9a93d8d58747d75a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141705"
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
 La mayoría de los métodos de nombre seguro devuelven un `true` simple o `false` indicación de la finalización correcta. Utilice la función `StrongNameErrorInfo` para recuperar un valor HRESULT que especifica el último error generado por las funciones de nombre seguro.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
