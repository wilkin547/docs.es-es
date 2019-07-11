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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6f495500b087b9e24936acd414f1aff463d7f64
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781074"
---
# <a name="strongnameerrorinfo-function"></a>StrongNameErrorInfo (Función)
Obtiene el último código de error generado por una de las funciones de nombres seguros.  
  
 Esta función está desusada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a>Valor devuelto  
 El último código de error de COM establecido por una de las funciones de nombre seguro.  
  
## <a name="remarks"></a>Comentarios  
 La mayoría de los métodos de nombre seguro devuelven una sencilla `true` o `false` indicación de una realización correcta. Use el `StrongNameErrorInfo` función para recuperar un valor HRESULT que especifica el último error generado por las funciones de nombre seguro.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: StrongName.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
