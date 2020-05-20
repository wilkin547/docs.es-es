---
title: ISymUnmanagedSymbolSearchInfo (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
ms.openlocfilehash: 308c501e17446719067d2dc0580d698c1770bf53
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610670"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a>ISymUnmanagedSymbolSearchInfo (Interfaz)
Proporciona métodos que obtienen información sobre la ruta de acceso de búsqueda. Obtenga esta interfaz mediante una llamada a `QueryInterface` en un objeto que implementa la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetHRESULT](isymunmanagedsymbolsearchinfo-gethresult-method.md)|Obtiene el HRESULT.|  
|[Método GetSearchPath](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|Obtiene la ruta de acceso de búsqueda.|  
|[Método GetSearchPathLength](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|Obtiene la longitud de la ruta de acceso de búsqueda.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
