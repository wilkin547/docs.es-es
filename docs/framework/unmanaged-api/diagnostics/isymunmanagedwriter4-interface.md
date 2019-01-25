---
title: ISymUnmanagedWriter4 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a5e44541a18f10588e899f59a166406c149691f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650059"
---
# <a name="isymunmanagedwriter4-interface"></a>ISymUnmanagedWriter4 (Interfaz)
ISymUnmanagedWriter4 (interfaz).  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a>Métodos  
 Esta interfaz contiene los siguientes métodos:  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetDebugInfoWithPadding (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|Funciona igual que [GetDebugInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) , salvo que la cadena de ruta de acceso se rellena con ceros que siguen el carácter nulo de terminación para que los datos de cadena de un tamaño fijo de `MAX_PATH`. Relleno solo se da si la longitud de cadena de ruta de acceso propio es menor que `MAX_PATH`.<br /><br /> Esto facilita la escritura herramientas que los archivos PE de diferencia.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también
- [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter3 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
