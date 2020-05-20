---
title: ISymUnmanagedAsyncMethod (Interfaz)
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: fef1af75587b889afad9cb5b93d0cd722294006b
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441817"
---
# <a name="isymunmanagedasyncmethod-interface"></a>ISymUnmanagedAsyncMethod (Interfaz)
Esta interfaz es el complemento de lectura de la [interfaz ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a>Métodos  
 Esta interfaz contiene los siguientes métodos:  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|Consulte [método defineasyncstepinfo (](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).|  
|[Método GetAsyncStepInfoCount](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|Consulte [método defineasyncstepinfo (](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).|  
|[Método GetCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|Consulte [método definecatchhandleriloffset (](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).|  
|[Método GetKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|Consulte [método definekickoffmethod (](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).|  
|[Método HasCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|Consulte [método definecatchhandleriloffset (](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).|  
|[Método IsAsyncMethod](isymunmanagedasyncmethod-isasyncmethod-method.md)|Comprueba si el método tiene información asincrónica o no.<br /><br /> Si este método devuelve `FALSE` , no es válido llamar a ningún otro método de esta interfaz. En este caso, todos devolverán `E_UNEXPECTED` .|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
