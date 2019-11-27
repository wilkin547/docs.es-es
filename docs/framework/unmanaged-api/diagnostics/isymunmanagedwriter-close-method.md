---
title: ISymUnmanagedWriter::Close (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
ms.openlocfilehash: cd601ac6041ca22d59d7467bafc7c1d87b21371f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428114"
---
# <a name="isymunmanagedwriterclose-method"></a>ISymUnmanagedWriter::Close (Método)
Cierra el escritor de símbolos después de confirmar los símbolos en el almacén de símbolos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="remarks"></a>Comentarios  
 Después de esta llamada, el escritor de símbolos deja de ser válido para actualizaciones adicionales. Para cerrar el escritor de símbolos sin confirmar los símbolos, utilice en su lugar el método [ISymUnmanagedWriter:: ABORT](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
