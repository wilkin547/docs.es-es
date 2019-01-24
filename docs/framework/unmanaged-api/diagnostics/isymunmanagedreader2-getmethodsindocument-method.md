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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 38cbea25c485ff517e3448c4de5245ff36fb5b21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594556"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a>ISymUnmanagedReader2::GetMethodsInDocument (Método)
Obtiene todos los métodos que tiene información de línea en el documento proporcionado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `document`  
 [in] Un puntero al documento.  
  
 `cMethod`  
 [in] Un `ULONG32` que indica el tamaño de la `pRetVal` matriz.  
  
 `pcMethod`  
 [out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los métodos.  
  
 `pRetVal`  
 [out] Un puntero al búfer que recibe los métodos.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también
- [ISymUnmanagedReader2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
