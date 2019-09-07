---
title: Funciones del asistente de Tlbexp (Referencia de la API no administrada)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a95ff535a4d0847fbd4b8af28f873b67a1829a4f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798826"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Funciones del asistente de Tlbexp (Referencia de la API no administrada)
La [herramienta Exportador de la biblioteca de tipos](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carga una biblioteca de vínculos dinámicos (DLL) denominada TlbRef.dll. Esta DLL contiene dos funciones auxiliares y una interfaz que usa la herramienta de exportación durante el proceso de conversión de ensamblado a biblioteca de tipos.  
  
## <a name="in-this-section"></a>En esta sección  
 [GetTypeLibInfo (Función)](gettypelibinfo-function.md)  
 Proporciona información de localización y sistema operativo para una biblioteca de tipos.  
  
 [LoadTypeLibWithResolver (Función)](loadtypelibwithresolver-function.md)  
 Carga una biblioteca de tipos mediante el uso de una implementación de la [interfaz ITypeLibResolver](itypelibresolver-interface.md) para resolver cualquier biblioteca de tipos a la que se haga referencia.  
  
 [ITypeLibResolver (interfaz)](itypelibresolver-interface.md)  
 Proporciona el [método ResolveTypeLib](resolvetypelib-method.md), que devuelve la ruta de acceso completa de una biblioteca de tipos.
