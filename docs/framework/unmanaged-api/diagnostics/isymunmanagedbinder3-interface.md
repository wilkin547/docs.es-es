---
title: ISymUnmanagedBinder3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdfd8e8fc419809a3a490639ada1c533f286fe8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157513"
---
# <a name="isymunmanagedbinder3-interface"></a>ISymUnmanagedBinder3 (Interfaz)
Extiende la interfaz de enlazador de símbolos. Esta interfaz se obtiene mediante una llamada a `QueryInterface` en un objeto que implementa el `ISymUnmanagedBinder` interfaz.  
  
> [!IMPORTANT]
>  Es un riesgo de seguridad para abrir un archivo de programa (PDB) de la base de datos desde un origen de confianza.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetReaderFromCallback (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|Permite al usuario implementar o proporcionar a través de la devolución de llamada, ya sea un `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` para obtener la información de directorio de depuración de la memoria|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [ISymUnmanagedBinder2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
