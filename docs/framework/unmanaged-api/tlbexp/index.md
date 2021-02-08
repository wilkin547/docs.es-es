---
description: 'Más información acerca de: Funciones del asistente de Tlbexp (Referencia de la API no administrada)'
title: Funciones del asistente de Tlbexp (Referencia de la API no administrada)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
ms.openlocfilehash: 8d5aacbe63d111b0b53f6bc76357a37ee4660d0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646262"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Funciones del asistente de Tlbexp (Referencia de la API no administrada)

La [herramienta Exportador de la biblioteca de tipos](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carga una biblioteca de vínculos dinámicos (DLL) denominada TlbRef.dll. Esta DLL contiene dos funciones auxiliares y una interfaz que usa la herramienta de exportación durante el proceso de conversión de ensamblado a biblioteca de tipos.  
  
## <a name="in-this-section"></a>En esta sección  

 [GetTypeLibInfo (Función)](gettypelibinfo-function.md)  
 Proporciona información de localización y sistema operativo para una biblioteca de tipos.  
  
 [LoadTypeLibWithResolver (Función)](loadtypelibwithresolver-function.md)  
 Carga una biblioteca de tipos mediante el uso de una implementación de la [interfaz ITypeLibResolver](itypelibresolver-interface.md) para resolver cualquier biblioteca de tipos a la que se haga referencia.  
  
 [ITypeLibResolver (Interfaz)](itypelibresolver-interface.md)  
 Proporciona el [método ResolveTypeLib](resolvetypelib-method.md), que devuelve la ruta de acceso completa de una biblioteca de tipos.
