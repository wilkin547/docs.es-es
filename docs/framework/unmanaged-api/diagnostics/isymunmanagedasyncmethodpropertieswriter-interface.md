---
title: ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82fcddd7a3f89a92cc79285930b30342333fbec2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112403"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a>ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)
Permite definir la información de método asincrónico opcional para cada símbolo de método. Utilice siempre con un método abierto; es decir, entre las llamadas a la [OpenMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) y [CloseMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a>Métodos  
 Esta interfaz contiene los siguientes métodos:  
  
|Método|Descripción|  
|------------|-----------------|  
|[DefineAsyncStepInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|Definir un grupo de async await operaciones en el método actual.<br /><br /> Cada desplazamiento yield coincide con la instrucción de devolución de una instrucción await, que identifica un rendimiento potencial. Cada `breakpointMethod` / `breakpointOffset` par identifica dónde se reanudará la operación asincrónica; puede estar en un método diferente.|  
|[DefineCatchHandlerILOffset (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|Establece el IL de desplazamiento para el controlador catch generado por el compilador que encapsula un método asincrónico.<br /><br /> Se usa el desplazamiento IL de catch generado por el depurador para controlar la captura como si fuera código de no usuario, aunque puede producir en un método de código de usuario. En concreto, se utiliza en respuesta a un **CatchHandlerFound** eventos de excepción.|  
|[DefineKickoffMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|Establece el método inicial que inicia la operación asincrónica.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
