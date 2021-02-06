---
description: 'Más información acerca de: EmitAssembly (método)'
title: EmitAssembly (Método)
ms.date: 03/30/2017
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
ms.openlocfilehash: aada17d8df6435c5edfe6beb5db5ee13f887f253
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638345"
---
# <a name="emitassembly-method"></a>EmitAssembly (Método)

Crea el ensamblado. Llame a este método después de que se cierren todos los demás archivos excepto el archivo de ensamblado. No llame a este método al producir módulos sin enlazar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  

 `AssemblyID`  
 IDENTIFICADOR del ensamblado.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
