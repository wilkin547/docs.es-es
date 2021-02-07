---
description: 'Más información acerca de: ISymUnmanagedWriter:: GetDebugInfo (método)'
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
ms.openlocfilehash: 2255cc90c0bfcd36dacdf81703af67d3f47739db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762323"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>ISymUnmanagedWriter::GetDebugInfo (Método)

Devuelve la información necesaria para que un compilador escriba la entrada del directorio de depuración en el encabezado de archivo portable ejecutable (PE). El escritor de símbolos rellena todos los campos excepto `TimeDateStamp` y `PointerToRawData` . (El compilador es responsable de establecer estos dos campos de forma adecuada).  
  
 Un compilador debe llamar a este método, emitir el BLOB de datos al archivo PE, establecer el `PointerToRawData` campo del IMAGE_DEBUG_DIRECTORY para que apunte a los datos emitidos y escribir el IMAGE_DEBUG_DIRECTORY en el archivo PE. El compilador también debe establecer el `TimeDateStamp` campo en el mismo valor del `TimeDateStamp` archivo PE que se está generando.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pIDD`  
 [in, out] Un puntero a un IMAGE_DEBUG_DIRECTORY que el escritor de símbolos rellenará.  
  
 `cData`  
 de Un `DWORD` que contiene el tamaño de los datos de depuración.  
  
 `pcData`  
 enuncia Un puntero a un `DWORD` que recibe el tamaño del búfer necesario para contener los datos de depuración.  
  
 `data`  
 enuncia Un puntero a un búfer que es lo suficientemente grande como para contener los datos de depuración para el almacén de símbolos.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)
