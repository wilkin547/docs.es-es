---
title: Procedimiento para compilar un ensamblado de varios archivos
description: Obtenga información sobre cómo compilar (crear) un ensamblado de varios archivos en .NET con código de ejemplo para ilustrar cada paso del procedimiento.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- Al.exe
- command-line compilers
- assembly manifest, multifile assemblies
- assemblies [.NET Framework], compiling
- Assembly Linker
- code modules
- multifile assemblies
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
ms.openlocfilehash: a4c298284950ba2989bb73e6d3383b3c4024e6e7
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104951"
---
# <a name="how-to-build-a-multifile-assembly"></a>Procedimiento para compilar un ensamblado de varios archivos

En este artículo se explica cómo crear un ensamblado de múltiples archivos e incluye código que muestra cada paso del procedimiento.

> [!NOTE]
> El IDE de Visual Studio para C# y Visual Basic solo se pueden utilizar para crear ensamblados de un solo archivo. Si desea crear ensamblados de múltiples archivos, debe usar compiladores de la línea de comandos o Visual Studio con Visual C++. Los ensamblados de varios archivos solo se admiten en .NET Framework.

## <a name="create-a-multifile-assembly"></a>Crear un ensamblado de varios archivos

1. Compile en módulos de código todos los archivos que contengan espacios de nombres a los que hacen referencia otros módulos del ensamblado. La extensión predeterminada de los módulos de código es *.netmodule*.

   Por ejemplo, supongamos que el archivo `Stringer` tiene un espacio de nombres denominado `myStringer`, que incluye una clase denominada `Stringer`. La clase `Stringer` contiene un método denominado `StringerMethod` que escribe una única línea en la consola.

   ```cpp
   // Assembly building example in the .NET Framework.
   using namespace System;

   namespace myStringer
   {
       public ref class Stringer
       {
       public:
           void StringerMethod()
           {
               System::Console::WriteLine("This is a line from StringerMethod.");
           }
       };
   }
   ```

   ```csharp
   // Assembly building example in the .NET Framework.
   using System;

   namespace myStringer
   {
       public class Stringer
       {
           public void StringerMethod()
           {
               System.Console.WriteLine("This is a line from StringerMethod.");
           }
       }
   }
   ```

   ```vb
   ' Assembly building example in the .NET Framework.
   Namespace myStringer
       Public Class Stringer
           Public Sub StringerMethod()
               System.Console.WriteLine("This is a line from StringerMethod.")
           End Sub
       End Class
   End Namespace
   ```

2. Use el comando siguiente para compilar este código:

   ```cpp
   cl /clr:pure /LN Stringer.cpp
   ```

   ```csharp
   csc /t:module Stringer.cs
   ```

   ```vb
   vbc /t:module Stringer.vb
   ```

   Si se especifica el parámetro *module* con la opción del compilador **/t:** , se indica que el archivo se debe compilar como un módulo y no como un ensamblado. El compilador produce un módulo denominado *Stringer.netmodule*, que se puede agregar a un ensamblado.

3. Compile los módulos restantes, usando las opciones de compilador necesarias para indicar los otros módulos a los que hace referencia el código. En este paso se usa la opción del compilador **/addmodule**.

   En el siguiente ejemplo, un módulo de código denominado *Client* tiene un método `Main` de punto de entrada que hace referencia a un método del módulo *Stringer.dll* creado en el paso 1.

   ```cpp
   #using "Stringer.netmodule"

   using namespace System;
   using namespace myStringer; //The namespace created in Stringer.netmodule.

   ref class MainClientApp
   {
       // Static method Main is the entry point method.
   public:
       static void Main()
       {
           Stringer^ myStringInstance = gcnew Stringer();
           Console::WriteLine("Client code executes");
           myStringInstance->StringerMethod();
       }
   };

   int main()
   {
       MainClientApp::Main();
   }
   ```

   ```csharp
   using System;
   using myStringer;

   class MainClientApp
   {
       // Static method Main is the entry point method.
       public static void Main()
       {
           Stringer myStringInstance = new Stringer();
           Console.WriteLine("Client code executes");
           myStringInstance.StringerMethod();
       }
   }
   ```

   ```vb
   Imports myStringer

   Class MainClientApp
       ' Static method Main is the entry point method.
       Public Shared Sub Main()
           Dim myStringInstance As New Stringer()
           Console.WriteLine("Client code executes")
           myStringInstance.StringerMethod()
       End Sub
   End Class
   ```

4. Use el comando siguiente para compilar este código:

   ```cpp
   cl /clr:pure /FUStringer.netmodule /LN Client.cpp
   ```

   ```csharp
   csc /addmodule:Stringer.netmodule /t:module Client.cs
   ```

   ```vb
   vbc /addmodule:Stringer.netmodule /t:module Client.vb
   ```

   Especifique la opción **/t:module**, ya que este módulo se va a agregar a un ensamblado en un paso posterior. Especifique la opción **/addmodule**, ya que el código de *Client* hace referencia a un espacio de nombres creado por el código en *Stringer.netmodule*. El compilador produce un módulo denominado *Client.netmodule* que contiene una referencia a otro módulo, *Stringer.netmodule*.

   > [!NOTE]
   > Los compiladores de C# y Visual Basic son compatibles con la creación directa de ensamblados de múltiples archivos mediante las dos siguientes sintaxis distintas.
   >
   > Dos compilaciones crean un ensamblado de dos archivos:
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /t:module Stringer.cs
   >   csc Client.cs /addmodule:Stringer.netmodule
   >   ```
   >
   >   ```vb
   >   vbc /t:module Stringer.vb
   >   vbc Client.vb /addmodule:Stringer.netmodule
   >   ```
   >
   > Una compilación crea un ensamblado de dos archivos:
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /out:Client.exe Client.cs /out:Stringer.netmodule Stringer.cs
   >   ```
   >
   >   ```vb
   >   vbc /out:Client.exe Client.vb /out:Stringer.netmodule Stringer.vb
   >   ```

5. Use la [herramienta Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) para crear el archivo de salida que contendrá el manifiesto del ensamblado. Este archivo contiene información de referencia de todos los módulos o recursos que forman parte del ensamblado.

    En el símbolo del sistema, escriba el siguiente comando:

    **al** \<*module name*> \<*module name*> … **/main:** \<*method name*> **/out:** \<*file name*> **/target:** \<*assembly file type*>

    En este comando, los argumentos de *nombre del módulo* especifican el nombre de todos los módulos que se van a incluir en el ensamblado. La opción **/main:** especifica el nombre del método que es el punto de entrada del ensamblado. La opción **/out:** especifica el nombre del archivo de salida, que contiene metadatos del ensamblado. La opción **/target:** especifica que el ensamblado es un archivo ejecutable de aplicación de consola ( *.exe*), un archivo ejecutable de Windows ( *.win*) o un archivo de biblioteca ( *.lib*).

    En el siguiente ejemplo, *Al.exe* crea un ensamblado que es un ejecutable de aplicación de consola denominado *myAssembly.exe*. Esta aplicación está formada por dos módulos denominados *Client.netmodule* y *Stringer.netmodule*, y por el archivo ejecutable llamado *myAssembly.exe*, que solo contiene metadatos del ensamblado. El punto de entrada del ensamblado es el método `Main` de la clase `MainClientApp`, el cual se encuentra en *Client.dll*.

    ```cmd
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe
    ```

    Se puede usar el [Desensamblador de MSIL (Ildasm.exe)](../tools/ildasm-exe-il-disassembler.md) para examinar el contenido de un ensamblado o determinar si un archivo es un ensamblado o un módulo.

## <a name="see-also"></a>Vea también

- [Creación de ensamblados](../../standard/assembly/create.md)
- [Cómo: Ver el contenido de un ensamblado](../../standard/assembly/view-contents.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md)
- [Ensamblados de varios archivos](multifile-assemblies.md)
