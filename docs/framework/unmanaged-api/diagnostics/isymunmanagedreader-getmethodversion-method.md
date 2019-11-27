---
title: ISymUnmanagedReader::GetMethodVersion (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
ms.openlocfilehash: fcaf748413321f684336543e60f735af69894b51
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436010"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a>ISymUnmanagedReader::GetMethodVersion (Método)
Obtiene la versión del método. La versión del método comienza en 1 y se incrementa cada vez que se vuelve a compilar el método. La recompilación puede producirse sin realizar cambios en el método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pMethod`  
 de Método para el que se va a obtener la versión.  
  
 `version`  
 enuncia Puntero a una variable que recibe la versión del método.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedReader (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
