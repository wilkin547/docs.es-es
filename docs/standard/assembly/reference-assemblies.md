---
title: Ensamblados de referencia
description: Obtenga información sobre los ensamblados de referencia, un tipo especial de ensamblados de .NET que contienen solo la superficie de la API pública de la biblioteca.
author: MSDN-WhiteKnight
ms.date: 09/12/2019
ms.technology: dotnet-standard
ms.openlocfilehash: 938942caf81c54a8aa9207dbe87559438ffb252e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79141073"
---
# <a name="reference-assemblies"></a>Ensamblados de referencia

*Los ensamblados de referencia*  son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de la API pública de la biblioteca. Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y las declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API. En cambio, los ensamblados normales se denominan *ensamblados de implementación*.

Los ensamblados de referencia no se pueden cargar para su ejecución, pero se pueden pasar como entrada del compilador de la misma manera que los ensamblados de implementación. Los ensamblados de referencia suelen distribuirse con el kit de desarrollo de software (SDK) de una plataforma o biblioteca determinada.

El uso de un ensamblado de referencia permite a los desarrolladores compilar programas que tienen como destino una versión de biblioteca específica sin tener el ensamblado de implementación completo para esa versión. Supongamos que solo tiene la versión más reciente de alguna biblioteca en el equipo, pero quiere compilar un programa que tenga como destino una versión anterior de dicha biblioteca. Si compila directamente en el ensamblado de implementación, podría usar accidentalmente miembros de la API que no están disponibles en la versión anterior. Y solo se daría cuenta del error al probar el programa en la máquina de destino. Si compila con el ensamblado de referencia para la versión anterior, obtendrá inmediatamente un error en tiempo de compilación.

Un ensamblado de referencia puede representar también un contrato; es decir, un conjunto de API que no se corresponde con el ensamblado de implementación concreto. Este ensamblado de referencia, denominado *ensamblado de contrato*, se puede usar para tener como destino varias plataformas que admiten el mismo conjunto de API. Por ejemplo, .NET Standard proporciona el ensamblado del contrato, *netstandard.dll*, que representa el conjunto de API comunes compartidas entre distintas plataformas .NET. Las implementaciones de estas API están contenidas en ensamblados diferentes en distintas plataformas, como *mscorlib. dll*  en .NET Framework o *System.Private.CoreLib.dll* en .NET Core. Una biblioteca que tiene como destino .NET Standard puede ejecutarse en todas las plataformas que admiten .NET Standard.

## <a name="using-reference-assemblies"></a>Uso de ensamblados de referencia

Para utilizar ciertas API del proyecto, debe agregar referencias a sus ensamblados. Puede agregar referencias a ensamblados de implementación o a ensamblados de referencia. Se recomienda usar los ensamblados de referencia siempre que estén disponibles. De este modo, se asegurará de que solo usa los miembros de la API admitidos en la versión de destino, diseñada para que la usen los diseñadores de API. El uso del ensamblado de referencia garantiza que no está tomando una dependencia de los detalles de implementación.

Los ensamblados de referencia de las bibliotecas de .NET Framework se distribuyen con los paquetes de destino. Puede obtenerlos descargando un instalador independiente o seleccionando un componente en el instalador de Visual Studio. Para más información, consulte [Instalación de .NET Framework para desarrolladores](../../framework/install/guide-for-developers.md). En .NET Core y .NET Standard, los ensamblados de referencia se descargan automáticamente según sea necesario (a través de NuGet) y se hace referencia a ellos. En .NET Core 3.0 y versiones posteriores, los ensamblados de referencia para la plataforma principal se encuentran en el paquete [Microsoft.NETCore.App.Ref](https://www.nuget.org/packages/Microsoft.NETCore.App.Ref) (el paquete [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App) se usa para las versiones anteriores a la 3.0). Para obtener más información, vea [Paquetes, metapaquetes y marcos de trabajo](../../core/packages.md) en la guía de .NET Core.

Cuando se agregan referencias a ensamblados de .NET Framework en Visual Studio mediante el cuadro de diálogo **Agregar referencia**, se selecciona un ensamblado de la lista y Visual Studio busca automáticamente los ensamblados de referencia correspondientes a la versión de la plataforma de destino seleccionada en el proyecto. Lo mismo se aplica a la hora de agregar referencias directamente en el proyecto de MSBuild mediante el elemento de proyecto [Reference ](/visualstudio/msbuild/common-msbuild-project-items#reference): solo tiene que especificar el nombre del ensamblado, no la ruta de acceso del archivo completa. Al agregar referencias a estos ensamblados en la línea de comandos mediante la opción del compilador `-reference` ([en C#](../../csharp/language-reference/compiler-options/reference-compiler-option.md) y en [Visual Basic](../../visual-basic/reference/command-line-compiler/reference.md)) o mediante el método <xref:Microsoft.CodeAnalysis.Compilation.AddReferences%2A?displayProperty=nameWithType> en la API de Roslyn, debe especificar manualmente los archivos de ensamblado de referencia para la versión de la plataforma de destino correcta. Los archivos de ensamblado de referencia de .NET Framework se encuentran en el directorio *%ProgramFiles(x86)%\\Reference Assemblies\\Microsoft\\Framework\\.NETFramework*. Para .NET Core, puede forzar la operación de publicación para copiar los ensamblados de referencia de la plataforma de destino en el subdirectorio *publish/refs* del directorio de salida. Para ello, establezca la propiedad de proyecto `PreserveCompilationContext` en `true`. A continuación, puede pasar estos archivos de ensamblado de referencia al compilador. El uso de `DependencyContext` del paquete [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/) puede ayudar a localizar sus rutas de acceso.

Dado que no contienen ninguna implementación, no se pueden cargar ensamblados de referencia para su ejecución. Si intenta hacerlo, se producirá una excepción <xref:System.BadImageFormatException?displayProperty=nameWithType>. Si quiere examinar el contenido de un ensamblado de referencia, puede cargarlo en el contexto de solo reflexión en .NET Framework (mediante el método <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType>) o en el contexto <xref:System.Reflection.MetadataLoadContext> en .NET Core.

## <a name="generating-reference-assemblies"></a>Generar ensamblados de referencia

Puede ser útil generar ensamblados de referencia para las bibliotecas cuando los clientes de estas necesiten compilar sus programas en muchas versiones diferentes de las bibliotecas. La distribución de los ensamblados de implementación para todas estas versiones puede no resultar práctica debido a su gran tamaño. Los ensamblados de referencia tienen un tamaño menor, por lo que distribuirlos como parte del SDK de la biblioteca reduce el tamaño de la descarga y ahorra espacio en disco.

Los IDE y las herramientas de compilación también pueden aprovechar los ensamblados de referencia para reducir los tiempos de compilación en el caso de soluciones de gran tamaño que se componen de varias bibliotecas de clases. Normalmente, en escenarios de compilación incremental, se vuelve a generar un proyecto cuando se modifica cualquiera de sus archivos de entrada, incluidos los ensamblados de los que depende. El ensamblado de implementación cambia cada vez que el programador cambia la implementación de cualquier miembro. El ensamblado de referencia solo cambia cuando se ve afectada su API pública. Por lo tanto, el uso del ensamblado de referencia como archivo de entrada en lugar del ensamblado de implementación permite omitir la compilación del proyecto dependiente en algunos casos.

Puede generar ensamblados de referencia:

- En un proyecto de MSBuild, mediante la propiedad de proyecto [`ProduceReferenceAssembly`](/visualstudio/msbuild/common-msbuild-project-properties).
- Al compilar el programa desde la línea de comandos, especificando las opciones de compilador `-refonly` ([C#](../../csharp/language-reference/compiler-options/refonly-compiler-option.md) / [Visual Basic](../../visual-basic/reference/command-line-compiler/refonly-compiler-option.md)) o `-refout` ([C#](../../csharp/language-reference/compiler-options/refout-compiler-option.md) / [Visual Basic](../../visual-basic/reference/command-line-compiler/refout-compiler-option.md)).
- Al usar la API de Roslyn, estableciendo <xref:Microsoft.CodeAnalysis.Emit.EmitOptions.EmitMetadataOnly?displayProperty=nameWithType> en `true` y <xref:Microsoft.CodeAnalysis.Emit.EmitOptions.IncludePrivateMembers?displayProperty=nameWithType> en `false` en un objeto que se pasa al método <xref:Microsoft.CodeAnalysis.Compilation.Emit%2A?displayProperty=nameWithType>.

Si quiere distribuir ensamblados de referencia con paquetes NuGet, debe incluirlos en el subdirectorio *ref \\* del directorio del paquete, en lugar de en el subdirectorio *lib \\* que se usa para los ensamblados de implementación.

## <a name="reference-assemblies-structure"></a>Estructura de ensamblados de referencia

Los ensamblados de referencia son una expansión del concepto relacionado: los *ensamblados de solo metadatos*. Los ensamblados de solo metadatos tienen sus cuerpos de métodos reemplazados por un cuerpo `throw null` único, pero incluyen todos los miembros excepto los tipos anónimos. El motivo de usar cuerpos `throw null` (en lugar de no usar ningún cuerpo) es que **PEVerify** pueda ejecutar y pasar (y, por lo tanto, validar la integridad de los metadatos).

Los ensamblados de referencia también quitan los metadatos (miembros privados) de los ensamblados de solo metadatos:

- Un ensamblado de referencia solo tiene referencias para lo que necesita en la superficie de la API. El ensamblado real puede tener referencias adicionales relacionadas con las implementaciones específicas. Por ejemplo, el ensamblado de referencia de `class C { private void M() { dynamic d = 1; ... } }` no hace referencia a ningún tipo necesario para `dynamic`.
- Los miembros de función privados (métodos, propiedades y eventos) se quitan en los casos donde su retirada no afecta a la compilación de manera visible. Si no hay ningún atributo [InternalsVisibleTo](xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute), también se quitan los miembros de función internos.

Los metadatos de los ensamblados de referencia continúan conservando la siguiente información:

- Todos los tipos, incluidos los tipos privados y anidados.
- Se conservan todos los atributos (incluso los internos).
- Todos los métodos virtuales.
- Implementaciones de interfaz explícitas.
- Eventos y propiedades implementados explícitamente, ya que sus descriptores de acceso son virtuales.
- Todos los campos de estructuras.

Los ensamblados de referencia incluyen un atributo[ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) de nivel de ensamblado. Este atributo puede especificarse en el origen. En tal caso, el compilador no necesitará sintetizarlo. Debido a este atributo, los tiempos de ejecución rechazarán cargar ensamblados de referencia para su ejecución (pero pueden cargarse en modo de solo reflexión).

Los detalles de la estructura de ensamblado de referencia exacta dependen de la versión del compilador. Las versiones más recientes pueden optar por excluir más metadatos si se determina que no afectan a la superficie de la API pública.

> [!NOTE]
> La información de esta sección solo es aplicable a los ensamblados de referencia generados por compiladores de Roslyn a partir de C# 7.1 o Visual Basic 15.3. La estructura de los ensamblados de referencia para las bibliotecas de .NET Framework y .NET Core puede diferir en algunos detalles porque utilizan su propio mecanismo de generación de ensamblados de referencia. Por ejemplo, podrían tener cuerpos de método totalmente vacíos en lugar del cuerpo `throw null`. Pero el principio general sigue siendo aplicable: no tienen implementaciones de método que se puedan usar y contienen metadatos solo para los miembros que tienen un impacto observable desde una perspectiva de API pública.

## <a name="see-also"></a>Vea también

- [Ensamblados de .NET](index.md)
- [Información general sobre destinos de Framework](/visualstudio/ide/visual-studio-multi-targeting-overview)
- [Cómo: Adición o eliminación de referencias con el Administrador de referencias](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)
