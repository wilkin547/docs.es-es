---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: ccf1287a1b0218e7f2560e1afbb0930c93b43263
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129173"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a>ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)
Establece el método de inicio que inicia la operación asincrónica.  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve `HRESULT`.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
