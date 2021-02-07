---
description: 'Más información acerca de: ISymUnmanagedWriter:: ABORT (método)'
title: ISymUnmanagedWriter::Abort (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
ms.openlocfilehash: 312694bf2b667ea78bf5ddc993d0e2b71c85a8ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762687"
---
# <a name="isymunmanagedwriterabort-method"></a>ISymUnmanagedWriter::Abort (Método)

Cierra el escritor de símbolos sin confirmar los símbolos en el almacén de símbolos. Después de esta llamada, el escritor de símbolos deja de ser válido para actualizaciones adicionales. Para confirmar los símbolos y cerrar el escritor de símbolos, utilice en su lugar el método [ISymUnmanagedWriter:: Close](isymunmanagedwriter-close-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)
