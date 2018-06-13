---
title: ISymUnmanagedBinder (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7bbdc4b1f15c8dbb154ed7b967bb21c61d11782a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425557"
---
# <a name="isymunmanagedbinder-interface"></a>ISymUnmanagedBinder (Interfaz)
Representa un enlazador de símbolos de código no administrado.  
  
> [!IMPORTANT]
>  Es un riesgo de seguridad para abrir un archivo de programa (PDB) de la base de datos desde un origen de confianza.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetReaderForFile (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|A partir de una interfaz de metadatos y un nombre de archivo, devuelve el valor correcto [ISymUnmanagedReader](isymunmanagedreader-interface.md) estructura que va a leer los símbolos de depuración asociados al módulo.|  
|[GetReaderFromStream (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|A partir de una interfaz de metadatos y una secuencia que contiene el almacén de símbolos, devuelve el valor correcto [ISymUnmanagedReader](isymunmanagedreader-interface.md) símbolos estructura que va a leer la depuración desde el almacén de símbolos especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedBinder2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [ISymUnmanagedBinder3 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
