---
title: ISymUnmanagedWriter2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
ms.openlocfilehash: 6feb48b7c78dda64ba372e470b83ffb14f21f2f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683334"
---
# <a name="isymunmanagedwriter2-interface"></a>ISymUnmanagedWriter2 (Interfaz)

Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables. Esta interfaz extiende la interfaz [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método DefineConstant2](isymunmanagedwriter2-defineconstant2-method.md)|Define un nombre para un valor constante.|  
|[Método DefineGlobalVariable2](isymunmanagedwriter2-defineglobalvariable2-method.md)|Define una única variable global.|  
|[Método DefineLocalVariable2](isymunmanagedwriter2-definelocalvariable2-method.md)|Define una única variable en el ámbito léxico actual.|  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)
- [ISymUnmanagedWriter3 (Interfaz)](isymunmanagedwriter3-interface.md)
