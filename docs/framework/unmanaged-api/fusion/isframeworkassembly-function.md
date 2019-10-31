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
ms.openlocfilehash: e30b6f2d2254d2d107c4c82a2c5664850ce6ec23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123067"
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
 de Nombre del ensamblado que se va a comprobar.  
  
 `pbIsFrameworkAssembly`  
 enuncia Valor booleano que indica si el ensamblado está administrado.  
  
 `pwzFrameworkAssemblyIdentity`  
 de Una cadena no canónica que contiene la identidad única del ensamblado.  
  
 `pccSize`  
 [in] Tamaño de `pwzFrameworkAssemblyIdentity`.  
  
## <a name="remarks"></a>Comentarios  
 El parámetro `pwzAssemblyReference` es un puntero a una cadena de caracteres que contiene el nombre de un ensamblado.  
  
 Si este ensamblado forma parte del .NET Framework, el parámetro `pbIsFrameworkAssembly` contendrá un valor booleano de `true`.  
  
 Si el ensamblado con nombre no forma parte de la .NET Framework, o si el parámetro `pwzAssemblyReference` no tiene un nombre de ensamblado, `pbIsFrameworkAssembly` contendrá un valor booleano de `false`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
