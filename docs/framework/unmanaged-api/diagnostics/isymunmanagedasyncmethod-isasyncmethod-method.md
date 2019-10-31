---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 0ea4c21e9e6a49d7bbbad5e1853598c440cd6410
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129211"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a>ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)
Comprueba si el método tiene información asincrónica o no.  
  
 Si este método devuelve `FALSE`, no es válido llamar a ningún otro método de esta interfaz. Todos devolverán `E_UNEXPECTED` en este caso.  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve `HRESULT`.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedAsyncMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
