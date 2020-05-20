---
title: ISymUnmanagedWriter::SetMethodSourceRange (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
ms.openlocfilehash: 4ba3f31ae6d6b67d7beaa2f709bf6174b721136d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609526"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a>ISymUnmanagedWriter::SetMethodSourceRange (Método)
Especifica el principio y final reales de un método dentro de un archivo de código fuente. Utilice este método para especificar la extensión de un método independientemente de los puntos de secuencia que existen dentro del método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a>Parámetros  
 `startDoc`  
 de Puntero al documento que contiene la posición inicial.  
  
 `startLine`  
 de Número de línea inicial.  
  
 `startColumn`  
 de Columna inicial.  
  
 `endDoc`  
 de Puntero al documento que contiene la posición final.  
  
 `endLine`  
 de El número de línea final.  
  
 `endColumn`  
 de Número de la columna final.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)
