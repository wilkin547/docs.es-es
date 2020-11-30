---
title: Procedimiento para crear ensamblados de confianza firmados
description: En este artículo se muestra cómo usar ensamblados de confianza con ensamblados que tienen nombres seguros. Se incluye información sobre la seguridad de .NET.
ms.date: 08/19/2019
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
dev_langs:
- csharp
- vb
ms.openlocfilehash: 4c441501ae0f939f69ac863a990d6e392bd35fc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734275"
---
# <a name="how-to-create-signed-friend-assemblies"></a>Procedimiento para crear ensamblados de confianza firmados

En este ejemplo se muestra cómo usar ensamblados de confianza con ensamblados que tienen nombres seguros. Ambos ensamblados deben tener nombres seguros. Aunque los dos ensamblados de este ejemplo usan las mismas claves, es posible usar claves diferentes para dos ensamblados.  
  
## <a name="create-a-signed-assembly-and-a-friend-assembly"></a>Creación de un ensamblado firmado y un ensamblado de confianza  
  
1. Abra un símbolo del sistema.  
  
2. Use la siguiente secuencia de comandos con la herramienta de nombre seguro para generar un archivo de claves y mostrar su clave pública. Para obtener más información, vea [Sn.exe (herramienta de nombre seguro)](../../framework/tools/sn-exe-strong-name-tool.md).  
  
    1. Genere una clave de nombre seguro para este ejemplo y almacénela en el archivo *FriendAssemblies.snk*:  
  
         `sn -k FriendAssemblies.snk`  
  
    2. Extraiga la clave pública de *FriendAssemblies.snk* y colóquela en *FriendAssemblies.publickey*:  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3. Muestre la clave pública almacenada en el archivo *FriendAssemblies.publickey*:  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. Cree un archivo de C# o de Visual Basic denominado *friend_signed_A* que contenga el código siguiente. El código usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para declarar *friend_signed_B* como un ensamblado de confianza.  

   La herramienta de nombre seguro genera una nueva clave pública cada vez que se ejecuta. Por tanto, debe reemplazar la clave pública en el código siguiente con la clave pública que acaba de generar, como se muestra en el ejemplo siguiente.  

   ```csharp  
   // friend_signed_A.cs  
   // Compile with:
   // csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
   using System.Runtime.CompilerServices;  

   [assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")]  
   class Class1  
   {  
       public void Test()  
       {  
           System.Console.WriteLine("Class1.Test");  
           System.Console.ReadLine();  
       }  
   }  
   ```  

   ```vb  
   ' friend_signed_A.vb  
   ' Compile with:
   ' Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
   Imports System.Runtime.CompilerServices  

   <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>
   Public Class Class1  
       Public Sub Test()  
           System.Console.WriteLine("Class1.Test")  
           System.Console.ReadLine()  
       End Sub  
   End Class  
   ```  

4. Compile y firme *friend_signed_A* mediante el siguiente comando.  

   ```csharp
   csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
   ```  

   ```vb
   Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
   ```  

5. Cree un archivo de C# o de Visual Basic denominado *friend_signed_B* que contenga el código siguiente. Dado que *friend_signed_A* especifica que *friend_signed_B* es un ensamblado de confianza, el código de *friend_signed_B* puede tener acceso a tipos y miembros de C# (`internal`) o Visual Basic (`Friend`) desde *friend_signed_A*. El archivo contiene el código siguiente.  

   ```csharp  
   // friend_signed_B.cs  
   // Compile with:
   // csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
   public class Program  
   {  
       static void Main()  
       {  
           Class1 inst = new Class1();  
           inst.Test();  
       }  
   }  
   ```  

   ```vb  
   ' friend_signed_B.vb  
   ' Compile with:
   ' Vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
   Module Sample  
       Public Sub Main()  
           Dim inst As New Class1  
           inst.Test()  
       End Sub  
   End Module  
   ```  

6. Compile y firme *friend_signed_B* mediante el siguiente comando.  

   ```csharp
   csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
   ```  

   ```vb
   vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
   ```  

   El nombre del ensamblado generado por el compilador debe coincidir con el nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Debe especificar explícitamente el nombre del ensamblado de salida ( *.exe* o *.dll*) mediante la opción `-out` del compilador. Para obtener más información, consulte [-out (Opciones del compilador de C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).  

7. Ejecute el archivo *friend_signed_B.exe*.  

   El programa imprime la cadena **Class1.Test**.  
  
## <a name="net-security"></a>Seguridad de .NET  

 Existen similitudes entre el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> y la clase <xref:System.Security.Permissions.StrongNameIdentityPermission>. La diferencia principal es que <xref:System.Security.Permissions.StrongNameIdentityPermission> puede exigir permisos de seguridad para ejecutar una sección determinada de código, mientras el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controla la visibilidad de los miembros y tipos `internal` (C#) o `Friend` (Visual Basic).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Ensamblados de .NET](index.md)
- [Ensamblados de confianza](friend.md)
- [Cómo: Crear ensamblados de confianza sin firmar](create-unsigned-friend.md)
- [-keyfile (C#)](../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)
- [-keyfile (Visual Basic)](../../visual-basic/reference/command-line-compiler/keyfile.md)
- [Sn.exe (herramienta de nombre seguro)](../../framework/tools/sn-exe-strong-name-tool.md)
- [Creación y uso de ensamblados con nombre seguro](create-use-strong-named.md)
- [Guía de programación de C#](../../csharp/programming-guide/index.md)
- [Conceptos de programación (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
