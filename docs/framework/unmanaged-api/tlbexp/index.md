---
title: Funciones auxiliares de Tlbexp (Referencia de la API no administrada)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f41a233e9b5338bdb0a324ff9af267a97821d4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Funciones auxiliares de Tlbexp (Referencia de la API no administrada)
El [herramienta Exportador de la biblioteca de tipo](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carga una biblioteca de vínculos dinámicos denominada TlbRef.dll. Este archivo DLL contiene dos funciones auxiliares y una interfaz que la herramienta exportador utiliza durante el proceso de conversión de ensamblado a biblioteca de tipos.  
  
## <a name="in-this-section"></a>En esta sección  
 [GetTypeLibInfo (Función)](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 Proporciona información de localización y el sistema operativo de una biblioteca de tipos.  
  
 [LoadTypeLibWithResolver (Función)](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 Carga una biblioteca de tipos mediante el uso de una implementación de la [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) resolver cualquier referencia a las bibliotecas de tipos.  
  
 [ITypeLibResolver (interfaz)](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 Proporciona el [ResolveTypeLib (método)](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), que devuelve la ruta de acceso completa de una biblioteca de tipos.
