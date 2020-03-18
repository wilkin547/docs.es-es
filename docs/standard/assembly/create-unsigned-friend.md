---
title: Procedimiento para crear ensamblados de confianza sin firmar
ms.date: 08/19/2019
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
dev_langs:
- csharp
- vb
ms.openlocfilehash: f8fec064507553b8208083578165965de2303a33
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74352433"
---
# <a name="how-to-create-unsigned-friend-assemblies"></a>Procedimiento para crear ensamblados de confianza sin firmar

En este ejemplo se muestra cómo usar ensamblados de confianza con ensamblados sin firmar.

## <a name="create-an-assembly-and-a-friend-assembly"></a>Creación de un ensamblado y un ensamblado de confianza

1. Abra un símbolo del sistema.

2. Cree un archivo de C# o de Visual Basic denominado *friend_unsigned_A* que contenga el código siguiente. El código usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para declarar *friend_unsigned_B* como un ensamblado de confianza.

   ```csharp
   // friend_unsigned_A.cs
   // Compile with:
   // csc /target:library friend_unsigned_A.cs
   using System.Runtime.CompilerServices;
   using System;

   [assembly: InternalsVisibleTo("friend_unsigned_B")]

   // Type is internal by default.
   class Class1
   {
       public void Test()
       {
           Console.WriteLine("Class1.Test");
       }
   }

   // Public type with internal member.
   public class Class2
   {
       internal void Test()
       {
           Console.WriteLine("Class2.Test");
       }
   }
   ```

   ```vb
   ' friend_unsigned_A.vb
   ' Compile with:
   ' vbc -target:library friend_unsigned_A.vb
   Imports System.Runtime.CompilerServices

   <Assembly: InternalsVisibleTo("friend_unsigned_B")>

   ' Friend type.
   Friend Class Class1
       Public Sub Test()
           Console.WriteLine("Class1.Test")
       End Sub
   End Class

   ' Public type with Friend member.
   Public Class Class2
       Friend Sub Test()
           Console.WriteLine("Class2.Test")
       End Sub
   End Class
   ```

3. Compile y firme *friend_unsigned_A* mediante el siguiente comando:

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. Cree un archivo de C# o de Visual Basic denominado *friend_unsigned_B* que contenga el código siguiente. Dado que *friend_unsigned_A* especifica que *friend_unsigned_B* es un ensamblado de confianza, el código de *friend_unsigned_B* puede tener acceso a tipos y miembros de C# (`internal`) o Visual Basic (`Friend`) desde *friend_unsigned_A*.

   ```csharp
   // friend_unsigned_B.cs
   // Compile with:
   // csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   public class Program
   {
       static void Main()
       {
           // Access an internal type.
           Class1 inst1 = new Class1();
           inst1.Test();

           Class2 inst2 = new Class2();
           // Access an internal member of a public type.
           inst2.Test();

           System.Console.ReadLine();
       }
   }
   ```

   ```vb
   ' friend_unsigned_B.vb
   ' Compile with:
   ' vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   Module Module1
       Sub Main()
           ' Access a Friend type.
           Dim inst1 As New Class1()
           inst1.Test()

           Dim inst2 As New Class2()
           ' Access a Friend member of a public type.
           inst2.Test()

           System.Console.ReadLine()
       End Sub
   End Module
   ```

5. Compile *friend_unsigned_B* mediante el siguiente comando.

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   El nombre del ensamblado que genera el compilador debe coincidir con el nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Debe especificar explícitamente el nombre del ensamblado de salida ( *.exe* o *.dll*) mediante la opción `-out` del compilador. Para obtener más información, consulte [-out (Opciones del compilador de C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).

6. Ejecute el archivo *friend_unsigned_B.exe*.

   El programa genera dos cadenas: **Class1.Test** y **Class2.Test**.

## <a name="net-security"></a>Seguridad de .NET

Existen similitudes entre el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> y la clase <xref:System.Security.Permissions.StrongNameIdentityPermission>. La diferencia principal es que <xref:System.Security.Permissions.StrongNameIdentityPermission> puede exigir permisos de seguridad para ejecutar una sección determinada de código, mientras el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controla la visibilidad de los miembros y tipos `internal` o `Friend` (Visual Basic).

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Ensamblados de .NET](index.md)
- [Ensamblados de confianza](friend.md)
- [Cómo: Crear ensamblados de confianza firmados](create-signed-friend.md)
- [Guía de programación de C#](../../csharp/programming-guide/index.md)
- [Conceptos de programación (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
