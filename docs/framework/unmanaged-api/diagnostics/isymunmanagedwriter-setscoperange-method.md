---
description: 'Más información acerca de: ISymUnmanagedWriter:: SetScopeRange ((método)'
title: ISymUnmanagedWriter::SetScopeRange (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
ms.openlocfilehash: 43cfbeaa0d366b9f2d25068cfa7b91a0fea8ac59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762063"
---
# <a name="isymunmanagedwritersetscoperange-method"></a>ISymUnmanagedWriter::SetScopeRange (Método)

Define el intervalo de desplazamiento del ámbito léxico especificado. El ámbito se convierte en el nuevo ámbito actual y se inserta en una pila de ámbitos. Los ámbitos deben formar una jerarquía. No se permite que los elementos del mismo nivel se superpongan.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a>Parámetros  

 `scopeId`  
 de Identificador de ámbito para el ámbito.  
  
 `startOffset`  
 de Desplazamiento, en bytes, de la primera instrucción del ámbito léxico desde el principio del método.  
  
 `endOffset`  
 de Desplazamiento, en bytes, de la última instrucción del ámbito léxico desde el principio del método.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="remarks"></a>Observaciones  

 [ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) devuelve un identificador de ámbito opaco que se puede usar con `ISymUnmanagedWriter::SetScopeRange` para definir el desplazamiento inicial y final de un ámbito en un momento posterior. En este caso, se omiten los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y [ISymUnmanagedWriter:: closescope (](isymunmanagedwriter-closescope-method.md) . Los identificadores de ámbito solo son válidos en el método actual.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)
