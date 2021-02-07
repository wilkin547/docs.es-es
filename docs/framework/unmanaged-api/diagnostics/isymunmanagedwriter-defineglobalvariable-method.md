---
description: 'Más información acerca de: ISymUnmanagedWriter::D método efineGlobalVariable'
title: ISymUnmanagedWriter::DefineGlobalVariable (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
ms.openlocfilehash: 70dccfed054a9ac79baf3f28683edc9a14d3cdf7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762388"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a>ISymUnmanagedWriter::DefineGlobalVariable (Método)

Define una única variable global.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Parámetros  

 `name`  
 de Puntero a `WCHAR` que define el nombre de la variable global.  
  
 `attributes`  
 de Atributos de la variable global.  
  
 `cSig`  
 de `ULONG32` Que indica el tamaño, en caracteres, del `signature` búfer.  
  
 `signature`  
 de Firma de la variable global.  
  
 `addrKind`  
 de Tipo de dirección.  
  
 `addr1`  
 de Primera dirección de la especificación de parámetro.  
  
 `addr2`  
 de Segunda dirección de la especificación de parámetro.  
  
 `addr3`  
 de Tercera dirección de la especificación de parámetro.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)
- [Método DefineLocalVariable](isymunmanagedwriter-definelocalvariable-method.md)
- [Método DefineGlobalVariable2](isymunmanagedwriter2-defineglobalvariable2-method.md)
