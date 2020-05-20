---
title: ISymENCUnmanagedMethod (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
ms.openlocfilehash: 54c8c7f5c3ba6b4afd4ff352a8afb947a92e2d61
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441882"
---
# <a name="isymencunmanagedmethod-interface"></a>ISymENCUnmanagedMethod (Interfaz)
Proporciona información para la característica editar y continuar.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetDocumentsForMethod](isymencunmanagedmethod-getdocumentsformethod-method.md)|Obtiene los documentos en los que este método tiene líneas.|  
|[Método GetDocumentsForMethodCount](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|Obtiene el número de documentos en los que este método tiene líneas.|  
|[Método GetFileNameFromOffset](isymencunmanagedmethod-getfilenamefromoffset-method.md)|Obtiene el nombre de archivo de la línea asociada a un desplazamiento.|  
|[Método GetLineFromOffset](isymencunmanagedmethod-getlinefromoffset-method.md)|Obtiene la información de línea asociada a un desplazamiento.|  
|[Método GetSourceExtentInDocument](isymencunmanagedmethod-getsourceextentindocument-method.md)|Obtiene la línea de inicio más pequeña y la línea de finalización más grande para el método en un documento específico.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
