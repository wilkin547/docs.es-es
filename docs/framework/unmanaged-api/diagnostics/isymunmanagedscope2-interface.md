---
description: 'Más información acerca de: interfaz ISymUnmanagedScope2'
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
ms.openlocfilehash: a15094da68b00dbec454b2f6a642ac333f9a34ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763155"
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
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedScope (Interfaz)](isymunmanagedscope-interface.md)
