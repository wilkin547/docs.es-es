---
description: 'Más información acerca de: ISymUnmanagedWriter::D método efineParameter'
title: ISymUnmanagedWriter::DefineParameter (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
ms.openlocfilehash: 1e42140e33a99b224ccf3eff7ea29b7aa3ff1b15
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762362"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a>ISymUnmanagedWriter::DefineParameter (Método)

Define un único parámetro en el método actual. El tipo de parámetro se toma de la posición del parámetro (Sequence) dentro de la Signatura del método.  
  
 Si los parámetros se definen en los metadatos de un método determinado, no es necesario volver a definirlos mediante este método. Los lectores de símbolos deben comprobar los metadatos normales de los parámetros antes de comprobar el almacén de símbolos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Parámetros  

 `name`  
 de Nombre del parámetro.  
  
 `attributes`  
 de Atributos de parámetro.  
  
 `sequence`  
 de Firma del parámetro.  
  
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
