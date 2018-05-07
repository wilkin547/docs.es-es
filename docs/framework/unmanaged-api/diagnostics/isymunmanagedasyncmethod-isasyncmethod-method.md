---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f5bf8252986ffa90ea5380d5342595cb91e5419
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a>ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)
Comprueba si el método tiene información de async o no.  
  
 Si este método devuelve `FALSE` , a continuación, no es válido para llamar a ningún otro método en esta interfaz. Lo harían devuelven todos los `E_UNEXPECTED` en este caso.  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve `HRESULT`.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [ISymUnmanagedAsyncMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
