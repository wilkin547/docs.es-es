---
description: 'Más información acerca de: ISymUnmanagedWriter2::D efineConstant2 (método)'
title: ISymUnmanagedWriter2::DefineConstant2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
ms.openlocfilehash: 9a0c444909055e18bdcd0b54fefbc8534ff8681e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761933"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a>ISymUnmanagedWriter2::DefineConstant2 (Método)

Define un nombre para un valor constante.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a>Parámetros  

 `name`  
 de El nombre de la constante.  
  
 `value`  
 de Valor de la constante.  
  
 `sigToken`  
 de Símbolo (token) de metadatos de la constante.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter2 (Interfaz)](isymunmanagedwriter2-interface.md)
- [Método DefineConstant](isymunmanagedwriter-defineconstant-method.md)
