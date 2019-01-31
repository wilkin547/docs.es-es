---
title: Compilar un proyecto de interoperabilidad
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a1e6ea8a7a7e6869ca9bc6c1b635f30574ac97f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695199"
---
# <a name="compiling-an-interop-project"></a>Compilar un proyecto de interoperabilidad

Los proyectos de interoperabilidad COM que hacen referencia a uno o más ensamblados que contienen tipos COM importados se compilan como cualquier otro proyecto administrado. Puede hacer referencia a ensamblados de interoperabilidad en un entorno de desarrollo como Visual Studio, o hacer referencia a ellos cuando se usa un compilador de línea de comandos. En cualquier caso, para compilar correctamente, el ensamblado de interoperabilidad debe estar en el mismo directorio que los demás archivos del proyecto.

 Hay dos maneras de hacer referencia a ensamblados de interoperabilidad:

-   Tipos de interoperabilidad insertados: a partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] y Visual Studio 2010, se puede indicar al compilador que inserte información de tipos de un ensamblado de interoperabilidad en el archivo ejecutable. Esta es la técnica recomendada.

-   Implementación de ensamblados de interoperabilidad: se puede crear una referencia estándar a un ensamblado de interoperabilidad. En este caso, el ensamblado de interoperabilidad debe implementarse con la aplicación.

 Las diferencias entre estas dos técnicas se explican con más detalle en [Usar tipos COM en código administrado](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)).

 La inserción de tipos de interoperabilidad con Visual Studio se describe en [Tutorial: Inserción de información de tipos de los ensamblados de Microsoft Office](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100)) y [Tutorial: Insertar los tipos de los ensamblados administrados](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).

 Para hacer referencia a un ensamblado de interoperabilidad con un compilador de línea de comandos e insertar información de tipos en los archivos ejecutables, use el modificador del compilador [/link (opciones del compilador de C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md) o [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md), y especifique el nombre del ensamblado de interoperabilidad.

> [!NOTE]
> Las aplicaciones de Visual C++ no pueden insertar información de tipos, pero pueden interoperar con aplicaciones o complementos que lo hagan.

 Para compilar una aplicación que incluye un ensamblado de interoperabilidad primario cuando se implementa, use el modificador del compilador **/reference** y especifique el nombre del ensamblado de interoperabilidad.

## <a name="see-also"></a>Vea también

- [Exponer componentes COM en .NET Framework](exposing-com-components.md)
- [Independencia del lenguaje y componentes independientes del lenguaje](../../standard/language-independence-and-language-independent-components.md)
- [Uso de tipos COM en código administrado](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))
- [Tutorial: Inserción de información de tipos de los ensamblados de Microsoft Office](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))
- [Tutorial: Inserción de tipos de ensamblados administrados](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)
- [Importar una biblioteca de tipos como un ensamblado](importing-a-type-library-as-an-assembly.md)