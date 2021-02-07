---
description: 'Más información acerca de: ISymUnmanagedWriter2::D efineLocalVariable2 (método)'
title: ISymUnmanagedWriter2::DefineLocalVariable2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
ms.openlocfilehash: 169a086b8420b5dbe20af8e16b21d5b41a958ead
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761816"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a>ISymUnmanagedWriter2::DefineLocalVariable2 (Método)

Define una única variable en el ámbito léxico actual. Se puede llamar a este método varias veces para una variable del mismo nombre que tiene varias casas en todo el ámbito. Sin embargo, en este caso, los valores de `startOffset` los `endOffset` parámetros y no deben superponerse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a>Parámetros  

 `name`  
 de Nombre de la variable local.  
  
 `attributes`  
 de Atributos de la variable local.  
  
 `sigToken`  
 de Símbolo (token) de metadatos de la firma.  
  
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

 **Encabezado:** CorSym. idl  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter2 (Interfaz)](isymunmanagedwriter2-interface.md)
- [Método DefineLocalVariable](isymunmanagedwriter-definelocalvariable-method.md)
