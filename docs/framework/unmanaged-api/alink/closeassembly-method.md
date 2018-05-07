---
title: CloseAssembly (Método)
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68698aab0fd0872c6e6f67e4ec531ab0226e784f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="closeassembly-method"></a>CloseAssembly (Método)
Finaliza las operaciones de montaje. Llamar a este método antes de comenzar un nuevo ensamblado o módulo no enlazado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 Identificador del ensamblado.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h.  
  
## <a name="see-also"></a>Vea también  
 [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
