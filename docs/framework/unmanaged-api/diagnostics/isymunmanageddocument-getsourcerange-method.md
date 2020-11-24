---
title: ISymUnmanagedDocument::GetSourceRange (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
ms.openlocfilehash: f5d7df60a7b9c728b73fe6592226a8b6734b1e66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692155"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a>ISymUnmanagedDocument::GetSourceRange (Método)

Devuelve el intervalo especificado del código fuente incrustado en el búfer especificado. El búfer debe ser lo suficientemente grande como para contener el origen.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `startLine`  
 de Línea inicial del documento actual.  
  
 `startColumn`  
 de Columna inicial del documento actual.  
  
 `endLine`  
 de Última línea del documento actual.  
  
 `endColumn`  
 de Columna final del documento actual.  
  
 `cSourceBytes`  
 de Tamaño del origen, en bytes.  
  
 `pcSourceBytes`  
 enuncia Puntero a una variable que recibe el tamaño de origen.  
  
 `source`  
 enuncia Tamaño y longitud del intervalo especificado del documento de origen, en bytes.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente.  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedDocument (Interfaz)](isymunmanageddocument-interface.md)
