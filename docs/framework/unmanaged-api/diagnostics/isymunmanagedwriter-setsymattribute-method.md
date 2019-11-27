---
title: ISymUnmanagedWriter::SetSymAttribute (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
ms.openlocfilehash: 8a4d205586921b377147eeab80754e1a0d9e52b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427844"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a>ISymUnmanagedWriter::SetSymAttribute (Método)
Define un atributo personalizado basado en su nombre. Estos atributos se guardan en el almacén de símbolos, a diferencia de los atributos personalizados de metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `parent`  
 de Token de metadatos para el que se define el atributo.  
  
 `name`  
 de Puntero a una `WCHAR` que contiene el nombre del atributo.  
  
 `cData`  
 de `ULONG32` que indica el tamaño de la matriz de `data`.  
  
 `data`  
 de Valor del atributo.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
