---
title: IsFrameworkAssembly (Función)
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 989d046bba1ba3170649e9d908a850bd1177fdd2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773830"
---
# <a name="isframeworkassembly-function"></a>IsFrameworkAssembly (Función)
Obtiene un valor que indica si el ensamblado especificado está administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzAssemblyReference`  
 [in] El nombre del ensamblado que se va a comprobar.  
  
 `pbIsFrameworkAssembly`  
 [out] Un valor booleano que indica si el ensamblado es administrado.  
  
 `pwzFrameworkAssemblyIdentity`  
 [in] Una cadena sin formato canónico que contiene la identidad única del ensamblado.  
  
 `pccSize`  
 [in] Tamaño de `pwzFrameworkAssemblyIdentity`.  
  
## <a name="remarks"></a>Comentarios  
 El `pwzAssemblyReference` parámetro es un puntero a una cadena de caracteres que contiene el nombre de un ensamblado.  
  
 Si este ensamblado forma parte de .NET Framework, el `pbIsFrameworkAssembly` parámetro contendrá un valor booleano de `true`.  
  
 Si el ensamblado con nombre no forma parte de .NET Framework, o si el `pwzAssemblyReference` parámetro no es un ensamblado, el nombre `pbIsFrameworkAssembly` contendrá un valor booleano de `false`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
