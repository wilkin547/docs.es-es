---
title: ISymUnmanagedReader2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: d4c5ff46d37b1292059b18920abd8042c18bbf31
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615402"
---
# <a name="isymunmanagedreader2-interface"></a>ISymUnmanagedReader2 (Interfaz)
Representa un lector de símbolos que proporciona acceso a los documentos, métodos y variables de un almacén de símbolos. Esta interfaz extiende la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetMethodByVersionPreRemap](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|Obtiene un método del lector de símbolos, dado un token de método y un número de versión de edición y continuación.|  
|[Método GetMethodsInDocument](isymunmanagedreader2-getmethodsindocument-method.md)|Obtiene todos los métodos que tienen información de línea en el documento proporcionado.|  
|[Método GetSymAttributePreRemap](isymunmanagedreader2-getsymattributepreremap-method.md)|Obtiene un atributo personalizado basado en su nombre.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedReader (Interfaz)](isymunmanagedreader-interface.md)
