---
description: Opciones del compilador de C# para controlar los archivos de entrada para la compilación. Estas opciones especifican cómo el compilador lee los metadatos de los ensamblados y módulos dependientes.
title: 'Opciones del compilador de C#: opciones de archivo de entrada'
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- References compiler option [C#]
- AddModules compiler option [C#]
- EmbedInteropTypes compiler option [C#]
ms.openlocfilehash: 819e2322720782b94bd744e00c602221f023c0d8
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482502"
---
# <a name="c-compiler-options-that-specify-inputs"></a>Opciones del compilador de C# que especifican entradas

Las opciones siguientes controlan las entradas del compilador. La nueva sintaxis de MSBuild se muestra en **negrita**. La sintaxis de *csc.exe* anterior se muestra en `code style`.

- **References** / `-reference` o `-references`: se hace referencia a los metadatos de los archivos de ensamblado especificados.
- **AddModules** / `-addmodule`: se agrega un módulo (creado con `target:module` para este ensamblado).
- **EmbedInteropTypes** / `-link`: se insertan metadatos de los archivos de ensamblado de interoperabilidad especificados.

## <a name="references"></a>Referencias

La opción **References** hace que el compilador importe información de tipo [public](../keywords/public.md) del archivo especificado al proyecto actual, lo que permite hacer referencia a metadatos de los archivos de ensamblado especificados.

```xml
<Reference Include="filename" />
```

 `filename` es el nombre de un archivo que contiene un manifiesto del ensamblado. Para importar más de un archivo, incluya un elemento **Reference** diferente para cada archivo. Puede definir un alias como un elemento secundario del elemento **Reference**:

```xml
<Reference Include="filename.dll">
  <Aliases>LS</Aliases>
</Reference>
```

En el ejemplo anterior, `LS` es el identificador de C# válido que representa un espacio de nombres raíz que contendrá todos los espacios de nombres en el archivo *filename.dll* del ensamblado. Los archivos que importe deben contener un manifiesto. Use [**AdditionalLibPaths**](advanced.md#additionallibpaths) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado. En el tema [**AdditionalLibPaths**](advanced.md#additionallibpaths) también se describen los directorios en los que el compilador busca ensamblados. Para que el compilador reconozca un tipo de un ensamblado (y no de un módulo), debe obligársele a que resuelva el tipo, lo que se puede conseguir si se define una instancia del tipo. Existen otras formas de que el compilador resuelva nombres de tipos en un ensamblado; por ejemplo, si se hereda de un tipo de un ensamblado, el compilador reconocerá el nombre del tipo. A veces es necesario hacer referencia a dos versiones diferentes del mismo componente desde un ensamblado. Para ello, use el elemento **Aliases** del elemento **References** de cada archivo para distinguir entre los dos archivos. Este alias se usará como calificador para el nombre del componente y se resolverá en el componente de uno de los archivos.

> [!NOTE]
> En Visual Studio, use el comando **Agregar referencia**. Para obtener más información, consulta [Procedimiento para agregar o quitar referencias mediante el Administrador de referencias](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).

## <a name="addmodules"></a>AddModules

Esta opción agrega un módulo que se ha creado con el modificador `<TargetType>module</TargetType>` para la compilación actual:

```xml
<AddModule Include=file1 />
<AddModule Include=file2 />
```

Donde `file`, `file2` son archivos de salida que contienen metadatos. El archivo no puede contener un manifiesto del ensamblado. Para importar más de un archivo, hay que separar los nombres de archivo con una coma o un punto y coma. Todos los módulos agregados con **AddModules** deben encontrarse en el mismo directorio que el archivo de salida en tiempo de ejecución. Es decir, puede especificar un módulo de cualquier directorio en el momento de la compilación, pero el módulo debe encontrarse en el directorio de la aplicación en tiempo de ejecución. Si el módulo no se encuentra en el directorio de la aplicación en tiempo de ejecución, obtendrá <xref:System.TypeLoadException>. `file` no puede contener ningún ensamblado. Por ejemplo, si el archivo de salida se ha creado con la opción [**TargetType**](output.md#targettype) de **module**, sus metadatos se pueden importar con **AddModules**.

Si el archivo de salida se ha creado con una opción [**TargetType**](output.md#targettype) diferente de **module**, no se podrán importar sus metadatos con **AddModules**, pero sí con [**References**](#references).

## <a name="embedinteroptypes"></a>EmbedInteropTypes

Hace que el compilador facilite al proyecto que se está compilando información de tipos COM en los ensamblados especificados.

```xml
<References>
  <EmbedInteropTypes>file1;file2;file3</EmbedInteropTypes>
</References>
```

Donde `file1;file2;file3` es una lista de nombres de archivo de ensamblado delimitados por signos de punto y coma. Si el nombre de archivo contiene un espacio, escríbalo entre comillas. La opción **EmbedInteropTypes** permite implementar una aplicación que tiene información de tipo insertada. La aplicación puede usar los tipos de un ensamblado en tiempo de ejecución que implementan la información de tipo incrustada sin necesidad de una referencia al ensamblado en tiempo de ejecución. Si hay varias versiones del ensamblado en tiempo de ejecución publicadas, la aplicación que contiene la información de tipo incrustada puede trabajar con las distintas versiones sin tener que volver a compilar. Para obtener un ejemplo, vea [Tutorial: Insertar los tipos de los ensamblados administrados](../../../standard/assembly/embed-types-visual-studio.md).

La opción **EmbedInteropTypes** resulta de especial utilidad cuando se trabaja con la interoperabilidad COM. Puede incrustar tipos COM para que la aplicación ya no necesite un ensamblado de interoperabilidad primario (PIA) en el equipo de destino. La opción **EmbedInteropTypes** indica al compilador que inserte la información de tipo COM del ensamblado de interoperabilidad al que se hace referencia en el código compilado resultante. El tipo COM se identifica mediante el valor de CLSID (GUID). Como resultado, la aplicación se puede ejecutar en un equipo de destino que tenga instalados los mismos tipos COM con los mismos valores de CLSID. Las aplicaciones que automatizan Microsoft Office son un buen ejemplo. Dado que las aplicaciones como Office suelen mantener el mismo valor de CLSID en las distintas versiones, la aplicación puede usar los tipos COM a los que se hace referencia siempre que .NET Framework 4 o posterior esté instalado en el equipo de destino y la aplicación emplee métodos, propiedades o eventos que estén incluidos en los tipos COM a los que se hace referencia. La opción **EmbedInteropTypes** solo inserta interfaces, estructuras y delegados. No se admite la inserción de clases COM.

> [!NOTE]
> Cuando se crea una instancia de un tipo COM incrustado en el código, hay que crear la instancia mediante la interfaz adecuada. Si se intenta crear una instancia de un tipo COM incrustado mediante la coclase, se produce un error.

Como sucede con la [opción del compilador **References**](#references), la opción del compilador **EmbedInteropTypes** usa el archivo de respuesta Csc.rsp, que hace referencia a ensamblados de .NET usados con frecuencia. Use la opción del compilador [**NoConfig**](miscellaneous.md#noconfig) si no quiere que el compilador utilice el archivo Csc.rsp.

[!code-csharp[VbLinkCompilerCS#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#1)]

Los tipos que tienen un parámetro genérico cuyo tipo se ha incrustado desde un ensamblado de interoperabilidad no se pueden usar si ese tipo pertenece a un ensamblado externo. Esta restricción no se aplica a las interfaces. Por ejemplo, considere la interfaz <xref:Microsoft.Office.Interop.Excel.Range> que se define en el ensamblado <xref:Microsoft.Office.Interop.Excel>. Si una biblioteca inserta tipos de interoperabilidad desde el ensamblado <xref:Microsoft.Office.Interop.Excel> y expone un método que devuelve un tipo genérico que tiene un parámetro cuyo tipo es la interfaz <xref:Microsoft.Office.Interop.Excel.Range>, ese método debe devolver una interfaz genérica, como se muestra en el ejemplo de código siguiente.

[!code-csharp[VbLinkCompilerCS#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs)]

En el ejemplo siguiente, el código de cliente puede llamar al método que devuelve la interfaz genérica <xref:System.Collections.IList> sin errores.

[!code-csharp[VbLinkCompilerCS#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#5)]
