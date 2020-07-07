---
title: Importar una biblioteca de tipos como un ensamblado
description: Importe una biblioteca de tipos, que contiene definiciones de tipos COM, como un ensamblado. Aprenda cómo crear metadatos a partir de una biblioteca de tipos, lo que da lugar a un ensamblado de interoperabilidad.
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- type metadata
- custom wrappers
- metadata
- exposing COM components to .NET Framework
- Type Library Importer
- interoperation with unmanaged code, importing type library
- interoperation with unmanaged code, exposing COM components
- type libraries
- TypeLibConverter class, importing type library as assembly
- COM interop, importing type library
- COM interop, exposing COM components
ms.assetid: d1898229-cd40-426e-a275-f3eb65fbc79f
ms.openlocfilehash: e5187e3c2ce533f25a38e93bc3715dd3e2e47c11
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622723"
---
# <a name="importing-a-type-library-as-an-assembly"></a>Importar una biblioteca de tipos como un ensamblado

Las definiciones de tipos COM residen normalmente en una biblioteca de tipos. Por el contrario, los compiladores conformes a CLS generan metadatos de tipos en un ensamblado. Las dos fuentes de información de tipos son muy diferentes. En este tema se describen técnicas para generar metadatos a partir de una biblioteca de tipos. El ensamblado resultante se denomina ensamblado de interoperabilidad y la información de tipos que contiene permite a las aplicaciones de .NET Framework usar tipos COM.

Hay dos maneras de hacer que esta información de tipos esté disponible para la aplicación:

- Mediante ensamblados de interoperabilidad solo de tiempo de diseño: A partir de .NET Framework 4, se puede indicar al compilador que inserte información de tipos del ensamblado de interoperabilidad en el archivo ejecutable. El compilador solo inserta la información de tipos que la aplicación usa. No es necesario implementar el ensamblado de interoperabilidad con la aplicación. Esta es la técnica recomendada.

- Mediante la implementación de ensamblados de interoperabilidad: se puede crear una referencia estándar al ensamblado de interoperabilidad. En este caso, el ensamblado de interoperabilidad debe implementarse con la aplicación. Si emplea esta técnica y no usa ningún componente COM privado, haga siempre referencia al ensamblado de interoperabilidad primario (PIA) publicado por el autor del componente COM que va a incorporar en el código administrado. Para más información sobre generar y usar ensamblados de interoperabilidad primarios, vea [Ensamblados de interoperabilidad primarios](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aax7sdch(v=vs.100)).

Al usar ensamblados de interoperabilidad solo de tiempo de diseño, se puede insertar información de tipos del ensamblado de interoperabilidad primario publicado por el autor del componente COM. En cambio, no es necesario implementar el ensamblado de interoperabilidad primario con la aplicación.

El uso de ensamblados de interoperabilidad solo de tiempo de diseño reduce el tamaño de la aplicación, dado que la mayoría de las aplicaciones no usa todas las características de un componente COM. El compilador es muy eficaz cuando inserta información de tipos; si la aplicación solo usa algunos de los métodos de una interfaz COM, el compilador no inserta los métodos que no se usan. Cuando una aplicación que contiene información de tipos insertada interactúa con otra aplicación, o interactúa con una aplicación que usa un ensamblado de interoperabilidad primario, Common Language Runtime usa reglas de equivalencia de tipos para determinar si dos tipos con el mismo nombre representan el mismo tipo de COM. No es necesario conocer estas reglas para usar los objetos COM. Si está interesado en las reglas, vea [Equivalencia de tipos y tipos de interoperabilidad incrustados](type-equivalence-and-embedded-interop-types.md).

## <a name="generating-metadata"></a>Generación de metadatos

Las bibliotecas de tipos COM pueden ser archivos independientes que tienen una extensión .tlb, como Loanlib.tlb. Algunas bibliotecas de tipos se insertan en la sección de recursos de un archivo .dll o .exe. Otros orígenes de información de biblioteca de tipos son los archivos .olb y .ocx.

Después de encontrar la biblioteca de tipos que contiene la implementación del tipo COM de destino, tiene las siguientes opciones para generar un ensamblado de interoperabilidad que contenga metadatos de tipos:

- Programa para la mejora

  Visual Studio convierte automáticamente los tipos COM de una biblioteca de tipos a metadatos en un ensamblado. Para obtener instrucciones, vea [Cómo: Adición de referencias a bibliotecas de tipos](how-to-add-references-to-type-libraries.md).

- [TlbImp.exe (Importador de la biblioteca de tipos)](../tools/tlbimp-exe-type-library-importer.md)

  El importador de la biblioteca de tipos proporciona opciones de línea de comandos para ajustar los metadatos en el archivo de interoperabilidad resultante, importa tipos desde una biblioteca de tipos existente y genera un ensamblado de interoperabilidad y un espacio de nombres. Para obtener instrucciones, vea [Cómo: Generar ensamblados de interoperabilidad a partir de bibliotecas de tipos](how-to-generate-interop-assemblies-from-type-libraries.md).

- Clase <xref:System.Runtime.InteropServices.TypeLibConverter?displayProperty=nameWithType>

  Esta clase proporciona métodos para convertir coclases e interfaces de una biblioteca de tipos en metadatos de un ensamblado. Genera el mismo resultado de metadatos que Tlbimp.exe. Pero a diferencia de Tlbimp.exe, la clase <xref:System.Runtime.InteropServices.TypeLibConverter> puede convertir una biblioteca de tipos en memoria en metadatos.

- Contenedores personalizados

  Cuando una biblioteca de tipos no está disponible o es incorrecta, una opción es crear una definición duplicada de la clase o interfaz en código fuente administrado. Después, se compila el código fuente con un compilador que tenga como destino el tiempo de ejecución para generar metadatos en un ensamblado.

  Para definir tipos COM manualmente, se debe tener acceso a los siguientes elementos:

  - Descripciones precisas de las coclases e interfaces que se van a definir.

  - Un compilador, como el compilador de C#, que pueda generar las definiciones de clase de .NET Framework correspondientes.

  - Conocimiento de las reglas de conversión de bibliotecas de tipos a ensamblados.

  Escribir un contenedor personalizado es una técnica avanzada. Para obtener información adicional sobre cómo generar un contenedor personalizado, vea [Personalizar contenedores estándar](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100)).

 Para más información sobre el proceso de importación de interoperabilidad COM, vea [Resumen de la conversión de bibliotecas de tipos en ensamblados](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)).

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.TypeLibConverter>
- [Exponer componentes COM en .NET Framework](exposing-com-components.md)
- [Resumen de la conversión de bibliotecas de tipos en ensamblados](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))
- [TlbImp.exe (Importador de la biblioteca de tipos)](../tools/tlbimp-exe-type-library-importer.md)
- [Personalización de contenedores estándar](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))
- [Uso de tipos COM en código administrado](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))
- [Compilar un proyecto de interoperabilidad](compiling-an-interop-project.md)
- [Implementar una aplicación interoperativa](deploying-an-interop-application.md)
- [Cómo: Agregar referencias a bibliotecas de tipos](how-to-add-references-to-type-libraries.md)
- [Cómo: Generar ensamblados de interoperabilidad a partir de bibliotecas de tipos](how-to-generate-interop-assemblies-from-type-libraries.md)
