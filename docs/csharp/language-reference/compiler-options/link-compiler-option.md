---
description: -link (Opciones del compilador de C#)
title: -link (Opciones del compilador de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- /l compiler option [C#]
- /link compiler option [C#]
- -l compiler option [C#]
- EmbedInteropTypes
- l compiler option [C#]
- embed interop types [COM Interop]
- -link compiler option [C#]
- link compiler option [C#]
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
ms.openlocfilehash: 0f6927fd240f3f8535478d163be615fc74dad8d2
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125402"
---
# <a name="-link-c-compiler-options"></a>-link (Opciones del compilador de C#)
Hace que el compilador facilite al proyecto que se está compilando información de tipos COM en los ensamblados especificados.

## <a name="syntax"></a>Sintaxis

```console
-link:fileList
// -or-
-l:fileList
```

## <a name="arguments"></a>Argumentos
 `fileList`  
 Obligatorio. Lista delimitada por comas de nombres de archivos de ensamblado. Si el nombre de archivo contiene un espacio, escríbalo entre comillas.

## <a name="remarks"></a>Comentarios
 La opción `-link` permite implementar una aplicación que tiene información de tipo incrustada. La aplicación puede usar los tipos de un ensamblado en tiempo de ejecución que implementan la información de tipo incrustada sin necesidad de una referencia al ensamblado en tiempo de ejecución. Si hay varias versiones del ensamblado en tiempo de ejecución publicadas, la aplicación que contiene la información de tipo incrustada puede trabajar con las distintas versiones sin tener que volver a compilar. Para obtener un ejemplo, vea [Tutorial: Insertar los tipos de los ensamblados administrados](../../../standard/assembly/embed-types-visual-studio.md).

 La opción `-link` resulta de especial utilidad cuando se trabaja con la interoperabilidad COM. Puede incrustar tipos COM para que la aplicación ya no necesite un ensamblado de interoperabilidad primario (PIA) en el equipo de destino. La opción `-link` indica al compilador que incruste la información de tipo COM del ensamblado de interoperabilidad al que se hace referencia en el código compilado resultante. El tipo COM se identifica mediante el valor de CLSID (GUID). Como resultado, la aplicación se puede ejecutar en un equipo de destino que tenga instalados los mismos tipos COM con los mismos valores de CLSID. Las aplicaciones que automatizan Microsoft Office son un buen ejemplo. Dado que las aplicaciones como Office suelen mantener el mismo valor de CLSID en las distintas versiones, la aplicación puede usar los tipos COM a los que se hace referencia siempre que .NET Framework 4 o posterior esté instalado en el equipo de destino y la aplicación emplee métodos, propiedades o eventos que estén incluidos en los tipos COM a los que se hace referencia.

 La opción `-link` incrusta únicamente interfaces, estructuras y delegados. No se admite la incrustación de clases COM.

> [!NOTE]
> Cuando se crea una instancia de un tipo COM incrustado en el código, hay que crear la instancia mediante la interfaz adecuada. Si se intenta crear una instancia de un tipo COM incrustado mediante la coclase, se produce un error.

 Para establecer la opción `-link` en Visual Studio, agregue una referencia de ensamblado y establezca la propiedad `Embed Interop Types` en **true**. El valor predeterminado de la propiedad `Embed Interop Types` es **false**.

 Si vincula a un ensamblado COM (ensamblado A) que a su vez hace referencia a otro ensamblado COM (ensamblado B), también debe vincular al ensamblado B si se cumple alguna de las siguientes condiciones:

- Un tipo del ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.

- Se invoca a un campo, una propiedad, un evento o un método que tiene un tipo de parámetro o un tipo de valor devuelto del ensamblado B.

 Al igual que la opción del compilador [-reference](./reference-compiler-option.md), la opción del compilador `-link` usa el archivo de respuesta Csc.rsp, que hace referencia a ensamblados de .NET Framework usados con frecuencia. Use la opción del compilador [-noconfig](./noconfig-compiler-option.md) si no quiere que el compilador emplee el archivo Csc.rsp.

 La forma abreviada de `-link` es `-l`.

## <a name="generics-and-embedded-types"></a>Tipos incrustados y genéricos
 En las secciones siguientes se describen las limitaciones sobre el uso de tipos genéricos en aplicaciones que incrustan tipos de interoperabilidad.

### <a name="generic-interfaces"></a>Interfaces genéricas
 No se puede usar interfaces genéricas que se incrusten desde un ensamblado de interoperabilidad. Esta implementación se muestra en el ejemplo siguiente.

 [!code-csharp[VbLinkCompilerCS#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#1)]

### <a name="types-that-have-generic-parameters"></a>Tipos que tienen parámetros genéricos
 Los tipos que tienen un parámetro genérico cuyo tipo se ha incrustado desde un ensamblado de interoperabilidad no se pueden usar si ese tipo pertenece a un ensamblado externo. Esta restricción no se aplica a las interfaces. Por ejemplo, considere la interfaz <xref:Microsoft.Office.Interop.Excel.Range> que se define en el ensamblado <xref:Microsoft.Office.Interop.Excel>. Si una biblioteca inserta tipos de interoperabilidad desde el ensamblado <xref:Microsoft.Office.Interop.Excel> y expone un método que devuelve un tipo genérico que tiene un parámetro cuyo tipo es la interfaz <xref:Microsoft.Office.Interop.Excel.Range>, ese método debe devolver una interfaz genérica, como se muestra en el ejemplo de código siguiente.

[!code-csharp[VbLinkCompilerCS#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs)]

 En el ejemplo siguiente, el código de cliente puede llamar al método que devuelve la interfaz genérica <xref:System.Collections.IList> sin errores.

 [!code-csharp[VbLinkCompilerCS#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#5)]

## <a name="example"></a>Ejemplo
 El código siguiente compila el archivo de origen `OfficeApp.cs` y hace referencia a ensamblados de `COMData1.dll` y `COMData2.dll` para generar `OfficeApp.exe`.

```csharp
csc -link:COMData1.dll,COMData2.dll -out:OfficeApp.exe OfficeApp.cs
```

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Tutorial: Inserción de tipos de ensamblados administrados](../../../standard/assembly/embed-types-visual-studio.md)
- [-reference (Opciones del compilador de C#)](./reference-compiler-option.md)
- [-noconfig (Opciones del compilador de C#)](./noconfig-compiler-option.md)
- [Compilar la línea de comandos con csc.exe](./command-line-building-with-csc-exe.md)
- [Información general sobre interoperabilidad](../../programming-guide/interop/interoperability-overview.md)
