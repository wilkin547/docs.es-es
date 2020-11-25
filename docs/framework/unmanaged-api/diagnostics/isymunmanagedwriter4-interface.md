---
title: ISymUnmanagedWriter4 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: c2b57897e4f0e8b23337302f344065d79677e0c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725812"
---
# <a name="isymunmanagedwriter4-interface"></a>ISymUnmanagedWriter4 (Interfaz)

Interfaz Isymunmanagedwriter4 (.  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a>Métodos  

 Esta interfaz contiene los siguientes métodos:  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetDebugInfoWithPadding](isymunmanagedwriter4-getdebuginfowithpadding-method.md)|Funciona igual que el [método GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md) , salvo que la cadena de ruta de acceso se rellena con ceros después del carácter nulo de terminación para convertir los datos de cadena en un tamaño fijo de `MAX_PATH` . El relleno solo se proporciona si la longitud de la cadena de ruta de acceso es menor que `MAX_PATH` .<br /><br /> Esto facilita la escritura de herramientas que diferencian los archivos PE.|  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter3 (Interfaz)](isymunmanagedwriter3-interface.md)
