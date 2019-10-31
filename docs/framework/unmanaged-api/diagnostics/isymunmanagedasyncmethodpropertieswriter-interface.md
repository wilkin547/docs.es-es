---
title: ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: db065357e22ac576600a3ca61dda0882b9206a86
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129163"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a>ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)
Permite definir información de método asincrónico opcional para cada símbolo de método. Siempre se usa con un método abierto; es decir, entre las llamadas al [método openmethod (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) y al [método CloseMethod (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a>Métodos  
 Esta interfaz contiene los siguientes métodos:  
  
|Método|Descripción|  
|------------|-----------------|  
|[DefineAsyncStepInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|Defina un grupo de operaciones de espera asincrónica en el método actual.<br /><br /> Cada desplazamiento yield coincide con una instrucción return de Await, que identifica un posible rendimiento. Cada `breakpointMethod`/par de `breakpointOffset` identifica dónde se reanudará la operación asincrónica; puede estar en un método diferente.|  
|[DefineCatchHandlerILOffset (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|Establece el desplazamiento IL para el controlador Catch generado por el compilador que ajusta un método asincrónico.<br /><br /> El depurador usa el desplazamiento IL de la captura generada para controlar la detección como si se tratara de código que no es de usuario, aunque puede producirse en un método de código de usuario. En concreto, se utiliza en respuesta a un evento de excepción **CatchHandlerFound** .|  
|[DefineKickoffMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|Establece el método de inicio que inicia la operación asincrónica.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
