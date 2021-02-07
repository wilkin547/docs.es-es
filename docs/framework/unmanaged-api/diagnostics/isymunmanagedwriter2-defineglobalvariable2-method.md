---
description: 'Más información acerca de: ISymUnmanagedWriter2::D efineGlobalVariable2 (método)'
title: ISymUnmanagedWriter2::DefineGlobalVariable2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
ms.openlocfilehash: 9a33ff8d452419ff103c9f4402620bd28196ae54
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761907"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a>ISymUnmanagedWriter2::DefineGlobalVariable2 (Método)

Define una única variable global.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Parámetros  

 `name`  
 de Nombre de la variable global.  
  
 `attributes`  
 de Atributos de la variable global.  
  
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
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter2 (Interfaz)](isymunmanagedwriter2-interface.md)
- [Método DefineGlobalVariable](isymunmanagedwriter-defineglobalvariable-method.md)
