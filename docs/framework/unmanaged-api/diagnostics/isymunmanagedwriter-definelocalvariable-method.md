---
description: 'Más información acerca de: ISymUnmanagedWriter::D método efineLocalVariable'
title: ISymUnmanagedWriter::DefineLocalVariable (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
ms.openlocfilehash: cd817e3002c2a55fd8bbd7e565283752926f746b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762375"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a>ISymUnmanagedWriter::DefineLocalVariable (Método)

Define una única variable en el ámbito léxico actual. Se puede llamar a este método varias veces para una variable del mismo nombre que tiene varias casas en todo el ámbito. Sin embargo, en este caso, los valores de `startOffset` los `endOffset` parámetros y no deben superponerse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a>Parámetros  

 `name`  
 de Puntero a `WCHAR` que define el nombre de la variable local.  
  
 `attributes`  
 de Atributos de la variable local.  
  
 `cSig`  
 de `ULONG32` Que indica el tamaño, en bytes, del `signature` búfer.  
  
 `signature`  
 de Firma de la variable local.  
  
 `addrKind`  
 de Tipo de dirección.  
  
 `addr1`  
 de Primera dirección de la especificación de parámetro.  
  
 `addr2`  
 de Segunda dirección de la especificación de parámetro.  
  
 `addr3`  
 de Tercera dirección de la especificación de parámetro.  
  
 `startOffset`  
 de Desplazamiento inicial de la variable. Este parámetro es opcional. Si es 0, este parámetro se omite y la variable se define en todo el ámbito. Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.  
  
 `endOffset`  
 de Desplazamiento final de la variable. Este parámetro es opcional. Si es 0, este parámetro se omite y la variable se define en todo el ámbito. Si es un valor distinto de cero, la variable se encuentra dentro de los desplazamientos del ámbito actual.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)
- [Método DefineGlobalVariable](isymunmanagedwriter-defineglobalvariable-method.md)
- [Método DefineLocalVariable2](isymunmanagedwriter2-definelocalvariable2-method.md)
