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
ms.openlocfilehash: 021fa1668247bc59a4412d2b5f4bac3f5ee8cc6b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799117"
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
 La mayoría de los métodos de nombre seguro devuelven un simple `true` o `false` una indicación de finalización correcta. Utilice la `StrongNameErrorInfo` función para recuperar un valor HRESULT que especifica el último error generado por las funciones de nombre seguro.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: StrongName. h  
  
 **Biblioteca** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
