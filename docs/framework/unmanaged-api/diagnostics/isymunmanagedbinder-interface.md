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
ms.openlocfilehash: f4f925282d65cd9cbc8eb1c8825f358602de68ed
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441700"
---
# <a name="isymunmanagedbinder-interface"></a>ISymUnmanagedBinder (Interfaz)
Representa un enlazador de símbolos para código no administrado.  
  
> [!IMPORTANT]
> Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md)|Dada una interfaz de metadatos y un nombre de archivo, devuelve la estructura [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo.|  
|[Método GetReaderFromStream](isymunmanagedbinder-getreaderfromstream-method.md)|Dada una interfaz de metadatos y una secuencia que contiene el almacén de símbolos, devuelve la estructura [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración del almacén de símbolos determinado.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder2 (Interfaz)](isymunmanagedbinder2-interface.md)
- [ISymUnmanagedBinder3 (Interfaz)](isymunmanagedbinder3-interface.md)
