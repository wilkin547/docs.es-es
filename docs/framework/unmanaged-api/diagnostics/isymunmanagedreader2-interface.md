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
ms.openlocfilehash: 3f34be833d3ccb5c636d2c5f18ccb6e216ef2c49
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709081"
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
  
## <a name="see-also"></a>Consulte también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedReader (Interfaz)](isymunmanagedreader-interface.md)
