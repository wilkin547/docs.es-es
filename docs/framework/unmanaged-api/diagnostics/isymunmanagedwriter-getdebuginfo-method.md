---
title: ISymUnmanagedWriter::GetDebugInfo (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.GetDebugInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1e9a2261ab5fd06e0514efdddf8a8e952a6e3d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>ISymUnmanagedWriter::GetDebugInfo (Método)
Devuelve la información necesaria para que un compilador escribir la entrada de directorio de depuración en el encabezado del archivo portable ejecutable (PE). El escritor de símbolos rellena todos los campos excepto `TimeDateStamp` y `PointerToRawData`. (El compilador es responsable de establecer correctamente estos dos campos).  
  
 Un compilador debe llamar a este método, emitir el blob de datos en el archivo PE, establezca el `PointerToRawData` campo IMAGE_DEBUG_DIRECTORY para apuntar a los datos emitidos y escribir IMAGE_DEBUG_DIRECTORY en el archivo PE. El compilador también debe establecer el `TimeDateStamp` campo para igualar la `TimeDateStamp` del archivo PE que se está generando.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pIDD`  
 [entrada, salida] Un puntero a IMAGE_DEBUG_DIRECTORY que van a rellenar el escritor de símbolos.  
  
 `cData`  
 [in] Un `DWORD` que contiene el tamaño de los datos de depuración.  
  
 `pcData`  
 [out] Un puntero a un `DWORD` que recibe el tamaño del búfer necesario para contener los datos de depuración.  
  
 `data`  
 [out] Un puntero a un búfer que es lo suficientemente grande como para contener los datos de depuración para el almacén de símbolos.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
