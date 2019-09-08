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
ms.openlocfilehash: 269e3702c21532f377735ba6087abb1603dde4f7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796319"
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
 El `pwzAssemblyReference` parámetro es un puntero a una cadena de caracteres que contiene el nombre de un ensamblado.  
  
 Si este ensamblado forma parte del .NET Framework, el `pbIsFrameworkAssembly` parámetro contendrá un valor booleano de `true`.  
  
 Si el ensamblado con nombre no forma parte de la .NET Framework, o `pwzAssemblyReference` si el parámetro no es un ensamblado, `pbIsFrameworkAssembly` contendrá un valor `false`booleano de.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
