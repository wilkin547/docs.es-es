---
description: 'Más información acerca de: interfaz ISymUnmanagedSymbolSearchInfo'
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
ms.openlocfilehash: 2f2ab198d2c54a9fcc5fa2e24b9196a38c583f81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762986"
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
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
