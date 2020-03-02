---
title: Escribir un programa en paralelo sencillo con Parallel.ForEach
ms.date: 02/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
ms.openlocfilehash: 02b94b673dc4468e68a1dadd83aab0e3bfcfaa16
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160305"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>Procedimiento Escribir un bucle Parallel.ForEach sencillo

Este ejemplo muestra cómo utilizar un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> para habilitar el paralelismo de datos sobre cualquier origen de datos <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.

> [!NOTE]
> En esta documentación, se utilizan expresiones lambda para definir delegados en PLINQ. Si no está familiarizado con las expresiones lambda de C# o Visual Basic, vea [Expresiones lambda en PLINQ y TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

## <a name="example"></a>Ejemplo

En este ejemplo se supone que tiene varios archivos .jpg en la carpeta *C:\Usuarios\Público\Imágenes\Imágenes de muestra* y crea una subcarpeta con el nombre *Modificadas*. Al ejecutar el ejemplo, gira cada imagen .jpg de *Imágenes de muestra* y la guarda en *Modificadas*. Puede modificar las dos rutas de acceso según sea necesario.

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

Un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> funciona como un bucle <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>. El bucle divide la colección de origen y programa el trabajo en varios subprocesos en función del entorno del sistema. Mientras más procesadores haya en el sistema, más rápido se ejecutará el método paralelo. Para algunas colecciones de origen, un bucle secuencial puede ser más rápido, dependiendo del tamaño del origen y del tipo de trabajo que realiza el bucle. Para más información sobre el rendimiento, vea [Problemas potenciales en el paralelismo de datos y tareas](potential-pitfalls-in-data-and-task-parallelism.md).

Para obtener más información sobre los bucles paralelos, vea [Procedimiento para escribir un bucle Parallel.For sencillo](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).

Para usar <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> con una colección no genérica, puede usar el método de extensión <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType> para convertir la colección en una colección genérica, como se muestra en el ejemplo siguiente:

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

También puede utilizar Parallel LINQ (PLINQ) para paralelizar el procesamiento de orígenes de datos <xref:System.Collections.Generic.IEnumerable%601>. PLINQ permite usar la sintaxis de consulta declarativa para expresar el comportamiento del bucle. Para más información, consulte [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).

## <a name="compile-and-run-the-code"></a>Compilación y ejecución del código

Puede compilar el código como una aplicación de consola de .NET Framework o como una aplicación de consola de .NET Core.

En Visual Studio, hay plantillas de aplicación de consola de Visual Basic y C# para Windows Desktop y .NET Core.

Desde la línea de comandos, puede usar la CLI de .NET Core y sus comandos (por ejemplo, `dotnet new console` o `dotnet new console -lang vb`). También puede crear el archivo y usar el compilador de línea de comandos para una aplicación de .NET Framework.

Para un proyecto de .NET Core, debe hacer referencia al paquete NuGet **System.Drawing.Common**. En Visual Studio, use el Administrador de paquetes de NuGet para instalar el paquete. Si lo prefiere, puede agregar una referencia al paquete en su archivo \*.csproj o \*.vbproj:

```xml
<ItemGroup>
     <PackageReference Include="System.Drawing.Common" Version="4.5.1" />
</ItemGroup>
```

Para ejecutar una aplicación de consola .NET Core desde la línea de comandos, use `dotnet run` desde la carpeta que contenga la aplicación.

Para ejecutar la aplicación de consola desde Visual Studio, presione **F5**.

## <a name="see-also"></a>Vea también

- [Paralelismo de datos (biblioteca TPL)](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [Programación en paralelo en .NET](../../../docs/standard/parallel-programming/index.md)
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
