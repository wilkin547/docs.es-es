---
title: "ISymUnmanagedWriter::GetDebugInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.GetDebugInfo
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 562e9015f2aa402a90a7b31e4b7002e68893a812
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
