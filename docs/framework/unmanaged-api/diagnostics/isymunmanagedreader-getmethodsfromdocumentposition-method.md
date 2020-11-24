---
title: ISymUnmanagedReader::GetMethodsFromDocumentPosition (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
ms.openlocfilehash: 5298dd0f53693d96b748f6c839660838fdfad4ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689555"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a>ISymUnmanagedReader::GetMethodsFromDocumentPosition (Método)

Devuelve una matriz de métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada de un documento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `document`  
 de Documento especificado.  
  
 `line`  
 de Línea del documento especificado.  
  
 `column`  
 de Columna del documento especificado.  
  
 `cMethod`  
 [in] Tamaño de la matriz `pRetVal`.  
  
 `pcMethod`  
 enuncia Puntero a una variable que recibe el número de elementos devueltos en la `pRetVal` matriz.  
  
 `pRetVal`  
 enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) que representa un método que contiene el punto de interrupción.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedReader (Interfaz)](isymunmanagedreader-interface.md)
