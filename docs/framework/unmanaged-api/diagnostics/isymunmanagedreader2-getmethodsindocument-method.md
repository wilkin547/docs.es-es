---
title: ISymUnmanagedReader2::GetMethodsInDocument (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
ms.openlocfilehash: 68a0f9ec8793d465a6fa3b1cb6936eddd7be4c8f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615415"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a>ISymUnmanagedReader2::GetMethodsInDocument (Método)
Obtiene todos los métodos que tienen información de línea en el documento proporcionado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `document`  
 de Puntero al documento.  
  
 `cMethod`  
 de `ULONG32`Que indica el tamaño de la `pRetVal` matriz.  
  
 `pcMethod`  
 enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los métodos.  
  
 `pRetVal`  
 enuncia Puntero al búfer que recibe los métodos.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [ISymUnmanagedReader2 (Interfaz)](isymunmanagedreader2-interface.md)
