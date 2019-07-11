---
title: ISymUnmanagedENCUpdate::InitializeForEnc (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.InitializeForEnc
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc
helpviewer_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc method [.NET Framework debugging]
- InitializeForEnc method [.NET Framework debugging]
ms.assetid: 796b2154-b53c-4d07-9e67-80fd6064725a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b6ca8482de1eaf021d65f63a349f37cff15f8ce
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774697"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a>ISymUnmanagedENCUpdate::InitializeForEnc (Método)
Permite que los límites del método que debe calcularse antes de la primera llamada a la [ISymUnmanagedENCUpdate:: Updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedENCUpdate (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
