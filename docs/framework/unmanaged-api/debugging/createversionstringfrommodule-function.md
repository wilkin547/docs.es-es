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
ms.openlocfilehash: 609d6e47c951aa104cb23084b65e98827a6851f1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789175"
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
  
## <a name="parameters"></a>Parameters  
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
  
## <a name="remarks"></a>Notas  
 Esta función acepta un proceso de CLR que se identifica mediante `pidDebuggee` y una ruta de acceso de cadena especificada por `szModuleName`. La cadena de versión se devuelve en el búfer al que `pBuffer` apunta. Esta cadena es opaca para el usuario de la función; es decir, no tiene ningún significado intrínseco en la propia cadena de versión. Se usa únicamente en el contexto de esta función y de la [función CreateDebuggingInterfaceFromVersion (](createdebugginginterfacefromversion-function-for-silverlight.md).  
  
 Se debe llamar dos veces a esta función. Cuando la llame por primera vez, pase NULL tanto para `pBuffer` como para `cchBuffer`. Al hacerlo, el tamaño del búfer necesario para `pBuffer` se devuelve en `pdwLength`. Después puede llamar a la función una segunda vez y pasar el búfer en `pBuffer` y su tamaño en `cchBuffer`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** dbgshim. h  
  
 **Biblioteca:** dbgshim. dll  
  
 **.NET Framework versiones:** 3,5 SP1
