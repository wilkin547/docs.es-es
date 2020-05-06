---
title: CreateVersionStringFromModule (Función)
ms.date: 03/30/2017
api_name:
- CreateVersionStringFromModule
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CreateVersionStringFromModule
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CreateVersionStringFromModule function
ms.assetid: 3d2fe9bd-75ef-4364-84a6-da1e1994ac1a
topic_type:
- apiref
ms.openlocfilehash: 60b7d77542a5065fb1e09a98e659cac17fb093e9
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860857"
---
# <a name="createversionstringfrommodule-function"></a>CreateVersionStringFromModule (Función)
Crea una cadena de versión a partir de una ruta de acceso de Common Language Runtime (CLR) en un proceso de destino.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateVersionStringFromModule (  
    [in]  DWORD      pidDebuggee,  
    [in]  LPCWSTR    szModuleName,  
    [out, size_is(cchBuffer),  
          length_is(*pdwLength)] LPWSTR Buffer,  
    [in]  DWORD      cchBuffer,  
    [out] DWORD*     pdwLength  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pidDebuggee`  
 [in] Identificador del proceso en el que se carga el CLR de destino.  
  
 `szModuleName`  
 [in] Ruta de acceso completa o relativa al CLR de destino que se carga en el proceso.  
  
 `pBuffer`  
 [out] Búfer de retorno para almacenar la cadena de versión del CLR de destino.  
  
 `cchBuffer`  
 [in] Tamaño de `pBuffer`.  
  
 `pdwLength`  
 [out] Longitud de la cadena de versión devuelta por `pBuffer`.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 La cadena de versión del CLR de destino se devolvió correctamente en `pBuffer`.  
  
 E_INVALIDARG  
 `szModuleName` es NULL, o bien `pBuffer` o `cchBuffer` es NULL. `pBuffer` y `cchBuffer` deben ser ambos NULL o no NULL.  
  
 HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)  
 `pdwLength` es mayor que `cchBuffer`. Este puede ser el resultado esperado si pasó NULL tanto para `pBuffer` como para `cchBuffer`, y consultó el tamaño del búfer necesario usando `pdwLength`.  
  
 HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)  
 `szModuleName` no contiene una ruta de acceso a un CLR válido en el proceso de destino.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 `pidDebuggee` no hace referencia a un proceso válido, u otro error.  
  
## <a name="remarks"></a>Comentarios  
 Esta función acepta un proceso de CLR que se identifica mediante `pidDebuggee` y una ruta de acceso de cadena especificada por `szModuleName`. La cadena de versión se devuelve en el búfer al que `pBuffer` apunta. Esta cadena es opaca para el usuario de la función; es decir, no tiene ningún significado intrínseco en la propia cadena de versión. Se usa únicamente en el contexto de esta función y de la [función CreateDebuggingInterfaceFromVersion (](createdebugginginterfacefromversion-function-for-silverlight.md).  
  
 Se debe llamar dos veces a esta función. Cuando la llame por primera vez, pase NULL tanto para `pBuffer` como para `cchBuffer`. Al hacerlo, el tamaño del búfer necesario para `pBuffer` se devuelve en `pdwLength`. Después puede llamar a la función una segunda vez y pasar el búfer en `pBuffer` y su tamaño en `cchBuffer`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** dbgshim. h  
  
 **Biblioteca:** dbgshim. dll  
  
 **.NET Framework versiones:** 3,5 SP1
