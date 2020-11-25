---
title: ISymUnmanagedBinder2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2 Interface
helpviewer_keywords:
- ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type:
- apiref
ms.openlocfilehash: c5a43f6c277f582f9f14cefe5bfba6f5300c09d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727359"
---
# <a name="isymunmanagedbinder2-interface"></a>ISymUnmanagedBinder2 (Interfaz)

Representa un enlazador de símbolos para código no administrado y extiende la interfaz [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) .  
  
> [!IMPORTANT]
> Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md)|Dada una interfaz de metadatos y un nombre de archivo, devuelve la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo. Proporciona una búsqueda más extensa que el método [ISymUnmanagedBinder:: GetReaderForFile (](isymunmanagedbinder-getreaderforfile-method.md) .|  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder (Interfaz)](isymunmanagedbinder-interface.md)
- [ISymUnmanagedBinder3 (Interfaz)](isymunmanagedbinder3-interface.md)
