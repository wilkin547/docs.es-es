---
title: LoadTypeLibWithResolver (Función)
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b78789344050fd5e1cb0ee3492bf330fbf92bc88
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798938"
---
# <a name="loadtypelibwithresolver-function"></a>LoadTypeLibWithResolver (Función)
Carga una biblioteca de tipos y usa la [interfaz ITypeLibResolver (](itypelibresolver-interface.md) proporcionada para resolver cualquier biblioteca de tipos a la que se hace referencia internamente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a>Parámetros  
 `szFile`  
 de Ruta de acceso del archivo de la biblioteca de tipos.  
  
 `regkind`  
 de Marca de [enumeración REGKIND](https://docs.microsoft.com/windows/win32/api/oleauto/ne-oleauto-regkind) que controla cómo se registra la biblioteca de tipos. Los valores posibles son:  
  
- `REGKIND_DEFAULT`: Usar el comportamiento de registro predeterminado.  
  
- `REGKIND_REGISTER`: Registre esta biblioteca de tipos.  
  
- `REGKIND_NONE`: No registre esta biblioteca de tipos.  
  
 `pTlbResolver`  
 de Puntero a la implementación de la [interfaz ITypeLibResolver (](itypelibresolver-interface.md).  
  
 `pptlib`  
 enuncia Referencia a la biblioteca de tipos que se está cargando.  
  
## <a name="return-value"></a>Valor devuelto  
 Uno de los valores HRESULT que se muestran en la tabla siguiente.  
  
|Valor devuelto|Significado|  
|------------------|-------------|  
|`S_OK`|Correcto.|  
|`E_OUTOFMEMORY`|Memoria insuficiente|  
|`E_POINTER`|Uno o varios de los punteros no son válidos.|  
|`E_INVALIDARG`|Uno o varios argumentos no son válidos.|  
|`TYPE_E_IOERROR`|La función no pudo escribir en el archivo.|  
|`TYPE_E_REGISTRYACCESS`|No se pudo abrir la base de datos de registro del sistema.|  
|`TYPE_E_INVALIDSTATE`|No se pudo abrir la biblioteca de tipos.|  
|`TYPE_E_CANTLOADLIBRARY`|No se pudo cargar la biblioteca de tipos o DLL.|  
  
## <a name="remarks"></a>Comentarios  
 [Tlbexp. exe (exportador](../../tools/tlbexp-exe-type-library-exporter.md) de la biblioteca de tipos) `LoadTypeLibWithResolver` llama a la función durante el proceso de conversión de ensamblado a biblioteca de tipos.  
  
 Esta función carga la biblioteca de tipos especificada con acceso mínimo al registro. A continuación, la función examina la biblioteca de tipos para las bibliotecas de tipos a las que se hace referencia internamente, cada una de las cuales se debe cargar y agregar a la biblioteca de tipos primaria.  
  
 Antes de que se pueda cargar una biblioteca de tipos a la que se hace referencia, su ruta de acceso al archivo de referencia debe resolverse en una ruta de acceso completa. Esto se logra mediante el [método resolvetypelib (](resolvetypelib-method.md) que proporciona la [interfaz ITypeLibResolver (](itypelibresolver-interface.md), que se pasa en el `pTlbResolver` parámetro.  
  
 Cuando se conoce la ruta de acceso completa del archivo de la biblioteca de tipos `LoadTypeLibWithResolver` a la que se hace referencia, la función carga y agrega la biblioteca de tipos a la biblioteca de tipos primaria, y crea una biblioteca de tipos maestra combinada.  
  
 Una vez que la función resuelve y carga todas las bibliotecas de tipos a las que se hace referencia internamente, devuelve una referencia a la biblioteca `pptlib` de tipos principal resuelta en el parámetro.  
  
 La función se llama generalmente mediante [Tlbexp. exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md), que proporciona su propia implementación interna de la `pTlbResolver` [interfaz ITypeLibResolver (](itypelibresolver-interface.md) en el parámetro. `LoadTypeLibWithResolver`  
  
 Si llama directamente `LoadTypeLibWithResolver` a, debe proporcionar su propia implementación de la [interfaz ITypeLibResolver (](itypelibresolver-interface.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: TlbRef. h  
  
 **Biblioteca** TlbRef.lib  
  
 **Versión de .NET Framework:** 3.5, 3.0, 2.0  
  
## <a name="see-also"></a>Vea también

- [Funciones del asistente Tlbexp](index.md)
- [LoadTypeLibEx función)](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
