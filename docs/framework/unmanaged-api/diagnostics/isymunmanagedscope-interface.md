---
description: 'Más información acerca de: ISymUnmanagedScope (interfaz)'
title: ISymUnmanagedScope (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: f1175656fb49ee16fd1cd676d08f6ebb76f40c6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763272"
---
# <a name="isymunmanagedscope-interface"></a>ISymUnmanagedScope (Interfaz)

Representa un ámbito léxico dentro de un método.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetChildren](isymunmanagedscope-getchildren-method.md)|Obtiene los elementos secundarios de este ámbito.|  
|[GetEndOffset (Método)](isymunmanagedscope-getendoffset-method.md)|Obtiene el desplazamiento final para este ámbito.|  
|[Método GetLocalCount](isymunmanagedscope-getlocalcount-method.md)|Obtiene un recuento de las variables locales definidas dentro de este ámbito.|  
|[Método GetLocals](isymunmanagedscope-getlocals-method.md)|Obtiene las variables locales definidas dentro de este ámbito.|  
|[Método GetMethod](isymunmanagedscope-getmethod-method.md)|Obtiene el método que contiene este ámbito.|  
|[Método GetNamespaces](isymunmanagedscope-getnamespaces-method.md)|Obtiene los espacios de nombres que se usan dentro de este ámbito.|  
|[Método GetParent](isymunmanagedscope-getparent-method.md)|Obtiene el ámbito primario de este ámbito.|  
|[Método GetStartOffset](isymunmanagedscope-getstartoffset-method.md)|Obtiene el desplazamiento inicial de este ámbito.|  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedScope2 (Interfaz)](isymunmanagedscope2-interface.md)
