---
title: "LoadTypeLibWithResolver (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f069d09f25575c39db097024384ad1bf14eaaf02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="loadtypelibwithresolver-function"></a>LoadTypeLibWithResolver (Función)
Carga una biblioteca de tipos y utiliza proporcionado [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) para resolver las bibliotecas de tipos que las que se hace referencia internamente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `szFile`  
 [in] La ruta de acceso de la biblioteca de tipos.  
  
 `regkind`  
 [in] A [enumeración REGKIND](https://msdn.microsoft.com/library/windows/desktop/ms221159.aspx) marca que controla cómo se registra la biblioteca de tipos. Sus valores posibles son:  
  
-   `REGKIND_DEFAULT`: Se usa el comportamiento de registro predeterminado.  
  
-   `REGKIND_REGISTER`: Registrar esta biblioteca de tipos.  
  
-   `REGKIND_NONE`: No registra esta biblioteca de tipos.  
  
 `pTlbResolver`  
 [in] Un puntero a la implementación de la [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).  
  
 `pptlib`  
 [out] Una referencia a la biblioteca de tipos que se va a cargar.  
  
## <a name="return-value"></a>Valor devuelto  
 Uno de los valores HRESULT enumerados en la tabla siguiente.  
  
|Valor devuelto|Significado|  
|------------------|-------------|  
|`S_OK`|Correcto.|  
|`E_OUTOFMEMORY`|Memoria insuficiente|  
|`E_POINTER`|Uno o varios de los punteros no son válidos.|  
|`E_INVALIDARG`|Uno o varios de los argumentos no son válidos.|  
|`TYPE_E_IOERROR`|La función no pudo escribir en el archivo.|  
|`TYPE_E_REGISTRYACCESS`|No se pudo abrir la base de datos de registro del sistema.|  
|`TYPE_E_INVALIDSTATE`|No se pudo abrir la biblioteca de tipos.|  
|`TYPE_E_CANTLOADLIBRARY`|No se pudo cargar la biblioteca de tipos o un archivo DLL.|  
  
## <a name="remarks"></a>Comentarios  
 El [Tlbexp.exe (exportador de la biblioteca de tipos)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) llamadas el `LoadTypeLibWithResolver` función durante el proceso de conversión de ensamblado a biblioteca de tipos.  
  
 Esta función carga la biblioteca de tipos especificada con acceso mínimo al registro. La función, a continuación, examina la biblioteca de tipos para las bibliotecas de tipo de referencia internamente, cada uno de los cuales debe cargarse y agregarse a la biblioteca de tipos de elemento primario.  
  
 Antes de que se puede cargar una biblioteca de tipos que se hace referencia, se debe resolver su ruta de acceso del archivo de referencia a una ruta de acceso completa al archivo. Esto se logra a través de la [ResolveTypeLib (método)](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) proporcionada por el [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), que se pasa en el `pTlbResolver` parámetro.  
  
 Cuando se conoce la ruta de acceso completa al archivo de la biblioteca de tipos que se hace referencia, la `LoadTypeLibWithResolver` función carga y agrega la biblioteca de tipos que se hace referencia a la biblioteca de tipos de elemento primario, crea una biblioteca de tipos combinada principal.  
  
 Después de la función resuelve y carga todas las bibliotecas de tipos que las que se hace referencia internamente, devuelve una referencia a la biblioteca de tipos principal en el `pptlib` parámetro.  
  
 El `LoadTypeLibWithResolver` función se denomina generalmente la [Tlbexp.exe (exportador de la biblioteca de tipos)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), lo que proporciona su propio interno [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementación en el `pTlbResolver` parámetro.  
  
 Si se llama a `LoadTypeLibWithResolver` directamente, debe proporcionar sus propios [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** TlbRef.h  
  
 **Biblioteca:** TlbRef.lib  
  
 **Versión de .NET framework:** 3.5, 3.0, 2.0  
  
## <a name="see-also"></a>Vea también  
 [Funciones auxiliares Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [Función LoadTypeLibEx de la](https://msdn.microsoft.com/library/windows/desktop/ms221249\(v=vs.85\).aspx)
