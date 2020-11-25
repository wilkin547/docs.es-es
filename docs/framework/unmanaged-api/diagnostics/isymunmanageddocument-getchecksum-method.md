---
title: ISymUnmanagedDocument::GetCheckSum (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
ms.openlocfilehash: 4030da31400b7075952d146e5d6740306863e9ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721093"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a>ISymUnmanagedDocument::GetCheckSum (Método)

Obtiene la suma de comprobación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cData`  
 de Longitud del búfer proporcionado por el parámetro. `data`  
  
 `pcData`  
 enuncia Tamaño y longitud de la suma de comprobación, en bytes.  
  
 `data`  
 enuncia Búfer que recibe la suma de comprobación.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, un código de error.  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedDocument (Interfaz)](isymunmanageddocument-interface.md)
