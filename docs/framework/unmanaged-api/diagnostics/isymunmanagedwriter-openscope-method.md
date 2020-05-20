---
title: ISymUnmanagedWriter::OpenScope (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type:
- apiref
ms.openlocfilehash: 4008b2a7d785781da5f35b3dc1e564487cb8e760
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609786"
---
# <a name="isymunmanagedwriteropenscope-method"></a>ISymUnmanagedWriter::OpenScope (Método)
Abre un nuevo ámbito léxico en el método actual. El ámbito se convierte en el nuevo ámbito actual y se inserta en una pila de ámbitos. Los ámbitos deben formar una jerarquía. No se permite que los elementos del mismo nivel se superpongan.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  
 `startOffset`  
 de Desplazamiento de la primera instrucción del ámbito léxico, en bytes, desde el principio del método.  
  
 `pRetVal`  
 enuncia Un puntero a un `ULONG32` que recibe el identificador de ámbito.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="remarks"></a>Observaciones  
 `ISymUnmanagedWriter::OpenScope`Devuelve un identificador de ámbito opaco que se puede usar con [ISymUnmanagedWriter:: SetScopeRange (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) para definir el desplazamiento inicial y final de un ámbito en un momento posterior. En este caso, se omiten los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y [ISymUnmanagedWriter:: closescope (](isymunmanagedwriter-closescope-method.md) . Los identificadores de ámbito solo son válidos en el método actual.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)
