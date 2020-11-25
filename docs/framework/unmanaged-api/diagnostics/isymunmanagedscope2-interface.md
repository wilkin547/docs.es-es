---
title: ISymUnmanagedScope2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
ms.openlocfilehash: 40c437e109eaa4352a83c5566185593cbc6b0eba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725838"
---
# <a name="isymunmanagedscope2-interface"></a>ISymUnmanagedScope2 (Interfaz)

Representa un ámbito léxico dentro de un método. Esta interfaz extiende la interfaz [ISymUnmanagedScope](isymunmanagedscope-interface.md) con métodos que obtienen información sobre las constantes definidas dentro del ámbito.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetConstantCount](isymunmanagedscope2-getconstantcount-method.md)|Obtiene un recuento de las constantes definidas dentro de este ámbito.|  
|[Método GetConstants](isymunmanagedscope2-getconstants-method.md)|Obtiene las constantes locales definidas dentro de este ámbito.|  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedScope (Interfaz)](isymunmanagedscope-interface.md)
