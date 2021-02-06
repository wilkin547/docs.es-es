---
description: 'Más información acerca de: StrongNameErrorInfo ((función)'
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
ms.openlocfilehash: a02e5f3d101a34c8ed13cb0f70fd2e95d945cb4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646405"
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
  
## <a name="remarks"></a>Observaciones  

 La mayoría de los métodos de nombre seguro devuelven un simple `true` o una `false` indicación de finalización correcta. Utilice la `StrongNameErrorInfo` función para recuperar un valor HRESULT que especifica el último error generado por las funciones de nombre seguro.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
