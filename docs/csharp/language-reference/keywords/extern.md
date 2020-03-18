---
title: 'Modificador extern: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- extern_CSharpKeyword
- extern
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
ms.openlocfilehash: c121d810e64b5fa27f105f814253c0752e028a95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713536"
---
# <a name="extern-c-reference"></a>extern (Referencia de C#)

El modificador `extern` se usa para declarar un método que se implementa externamente. Un uso común del modificador `extern` es con el atributo `DllImport` al usar servicios de interoperabilidad para llamar a código no administrado. En este caso, el método se debe declarar también como `static`, como se muestra en el ejemplo siguiente:

```csharp
[DllImport("avifil32.dll")]
private static extern void AVIFileInit();
```

La palabra clave `extern` también puede definir un alias del ensamblado externo, lo que permite hacer referencia a diferentes versiones del mismo componente desde un único ensamblado. Para obtener más información, vea [alias externo](extern-alias.md).

Es un error usar los modificadores [abstract](abstract.md) y `extern` juntos para modificar el mismo miembro. El uso del modificador `extern` significa que el método se implementa fuera del código de C#, mientras que el uso del modificador `abstract` significa que la implementación del método no se proporciona en la clase.

La palabra clave extern tiene usos más limitados en C# que en C++. Para comparar la palabra clave de C# con la de C++, consulte el tema sobre el uso de extern para especificar vinculación en la referencia del lenguaje C++.

## <a name="example-1"></a>Ejemplo 1

En este ejemplo, el programa recibe una cadena del usuario y la muestra en un cuadro de mensaje. El programa usa el método `MessageBox` importado de la biblioteca User32.dll.

[!code-csharp[csrefKeywordsModifiers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#8)]

## <a name="example-2"></a>Ejemplo 2

En este ejemplo se muestra un programa de C# que llama a una biblioteca de C (una DLL nativa).

1. Cree el archivo de C siguiente y denomínelo `cmdll.c`:

    ```c
    // cmdll.c
    // Compile with: -LD
    int __declspec(dllexport) SampleMethod(int i)
    {
      return i*10;
    }
    ```

2. Abra una ventana del símbolo del sistema de las herramientas nativas de Visual Studio x64 (o x32) desde el directorio de instalación de Visual Studio y compile el archivo `cmdll.c` escribiendo **cl -LD cmdll.c** en el símbolo del sistema.

3. En el mismo directorio, cree el siguiente archivo de C# y denomínelo `cm.cs`:

    ```csharp
    // cm.cs
    using System;
    using System.Runtime.InteropServices;
    public class MainClass
    {
        [DllImport("Cmdll.dll")]
          public static extern int SampleMethod(int x);

        static void Main()
        {
            Console.WriteLine("SampleMethod() returns {0}.", SampleMethod(5));
        }
    }
    ```

4. Abra una ventana del símbolo del sistema de las herramientas nativas de Visual Studio x64 (o x32) del directorio de instalación de Visual Studio y compile el archivo `cm.cs` escribiendo:

    > **csc cm.cs** (para el símbolo del sistema x64), o bien **csc -platform:x86 cm.cs** (para el símbolo del sistema x32)

    De esta forma, se creará el archivo ejecutable `cm.exe`.

5. Ejecute `cm.exe`. El método `SampleMethod` pasa el valor 5 al archivo DLL, que devuelve el valor multiplicado por 10.  El programa produce el siguiente resultado:

    ```output
    SampleMethod() returns 50.
    ```

## <a name="c-language-specification"></a>especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>
- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Modificadores](index.md)
