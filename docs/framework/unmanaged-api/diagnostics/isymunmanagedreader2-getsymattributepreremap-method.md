---
title: ISymUnmanagedReader2::GetSymAttributePreRemap (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
ms.openlocfilehash: 4009f8988c90ed090c0cc3d86164af347055722f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446421"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a>ISymUnmanagedReader2::GetSymAttributePreRemap (Método)
Obtiene un atributo personalizado basado en su nombre. A diferencia de los atributos personalizados de metadatos, estos atributos se guardan en el almacén de símbolos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `parent`  
 de Token de metadatos del elemento primario.  
  
 `name`  
 de Puntero a una `WCHAR` que contiene el nombre.  
  
 `cBuffer`  
 de `ULONG32` que indica el tamaño de la matriz de `buffer`.  
  
 `pcBuffer`  
 enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los bytes de atributo.  
  
 `buffer`  
 enuncia Puntero al búfer que recibe los bytes de atributo.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedReader2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
