---
title: Compilar un proyecto de interoperabilidad
description: Revise cómo compilar un proyecto de interoperabilidad COM, que se compila como un proyecto administrado si hace referencia a uno o varios ensamblados que contienen tipos COM importados.
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
ms.openlocfilehash: 1cf5bdbedd53227e812b0d2ed97778ab34a81444
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557102"
---
# <a name="compiling-an-interop-project"></a>Compilar un proyecto de interoperabilidad

Los proyectos de interoperabilidad COM que hacen referencia a uno o más ensamblados que contienen tipos COM importados se compilan como cualquier otro proyecto administrado. Puede hacer referencia a ensamblados de interoperabilidad en un entorno de desarrollo como Visual Studio, o hacer referencia a ellos cuando se usa un compilador de línea de comandos. En cualquier caso, para compilar correctamente, el ensamblado de interoperabilidad debe estar en el mismo directorio que los demás archivos del proyecto.

 Hay dos maneras de hacer referencia a ensamblados de interoperabilidad:

- Tipos de interoperabilidad insertados: A partir de .NET Framework 4 y Visual Studio 2010, se puede indicar al compilador que inserte información de tipos de un ensamblado de interoperabilidad en el archivo ejecutable. Esta es la técnica recomendada.

- Implementación de ensamblados de interoperabilidad: se puede crear una referencia estándar a un ensamblado de interoperabilidad. En este caso, el ensamblado de interoperabilidad debe implementarse con la aplicación.

 Las diferencias entre estas dos técnicas se explican con más detalle en [Usar tipos COM en código administrado](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).

 La inserción de tipos de interoperabilidad con Visual Studio se describe en [Tutorial: Insertar tipos de ensamblados administrados en Visual Studio](../../standard/assembly/embed-types-visual-studio.md).

 Para hacer referencia a un ensamblado de interoperabilidad con un compilador de línea de comandos e insertar información de tipos en los archivos ejecutables, use el modificador del compilador [-link (opciones del compilador de C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md) o [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md), y especifique el nombre del ensamblado de interoperabilidad.

> [!NOTE]
> Las aplicaciones de Visual C++ no pueden insertar información de tipos, pero pueden interoperar con aplicaciones o complementos que lo hagan.

 Para compilar una aplicación que incluye un ensamblado de interoperabilidad primario cuando se implementa, use el modificador del compilador **/reference** y especifique el nombre del ensamblado de interoperabilidad.

## <a name="see-also"></a>Vea también

- [Exponer componentes COM en .NET Framework](exposing-com-components.md)
- [Independencia del lenguaje y componentes independientes del lenguaje](../../standard/language-independence-and-language-independent-components.md)
- [Uso de tipos COM en código administrado](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))
- [Tutorial: Insertar tipos de ensamblados administrados en Visual Studio](../../standard/assembly/embed-types-visual-studio.md)
- [Importar una biblioteca de tipos como un ensamblado](importing-a-type-library-as-an-assembly.md)
