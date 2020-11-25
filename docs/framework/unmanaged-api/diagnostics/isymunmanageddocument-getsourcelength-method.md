---
title: ISymUnmanagedDocument::GetSourceLength (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
ms.openlocfilehash: c384fe6c4357c63bc56f9f9b1cc907dea64fddf7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700943"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a>ISymUnmanagedDocument::GetSourceLength (Método)

Obtiene la longitud, en bytes, del código fuente incrustado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pRetVal`  
 enuncia Puntero a una variable que indica la longitud, en bytes, del código fuente incrustado.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente.  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedDocument (Interfaz)](isymunmanageddocument-interface.md)
