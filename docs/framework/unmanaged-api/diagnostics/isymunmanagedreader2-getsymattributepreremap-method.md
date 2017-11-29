---
title: "ISymUnmanagedReader2::GetSymAttributePreRemap (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2.GetSymAttributePreRemap
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 75608d89b6fd34570166718de824150b0621c84e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a>ISymUnmanagedReader2::GetSymAttributePreRemap (Método)
Obtiene un atributo personalizado basándose en su nombre. A diferencia de los atributos personalizados de metadatos, estos atributos se encuentran en el almacén de símbolos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `parent`  
 [in] El token de metadatos del elemento primario.  
  
 `name`  
 [in] Un puntero a un `WCHAR` que contiene el nombre.  
  
 `cBuffer`  
 [in] A `ULONG32` que indica el tamaño de la `buffer` matriz.  
  
 `pcBuffer`  
 [out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los bytes del atributo.  
  
 `buffer`  
 [out] Un puntero al búfer que recibe los bytes del atributo.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [ISymUnmanagedReader2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
