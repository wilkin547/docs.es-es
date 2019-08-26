---
title: Procedimiento para crear ensamblados de confianza firmados (C#)
ms.date: 07/20/2015
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
ms.openlocfilehash: 7715726a200150b044fb8e97216fa02d0e784838
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595927"
---
# <a name="how-to-create-signed-friend-assemblies-c"></a>Procedimiento para crear ensamblados de confianza firmados (C#)
En este ejemplo se muestra cómo usar ensamblados de confianza con ensamblados que tienen nombres seguros. Ambos ensamblados deben tener nombres seguros. Aunque los dos ensamblados de este ejemplo usan las mismas claves, es posible usar claves diferentes para dos ensamblados.  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a>Para crear un ensamblado con signo y un ensamblado de confianza  
  
1. Abra un símbolo del sistema.  
  
2. Use la siguiente secuencia de comandos con la herramienta de nombre seguro para generar un archivo de claves y mostrar su clave pública. Para obtener más información, vea [Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md).  
  
    1. Genere una clave de nombre seguro para este ejemplo y almacénela en el archivo FriendAssemblies.snk:  
  
         `sn -k FriendAssemblies.snk`  
  
    2. Extraiga la clave pública de FriendAssemblies.snk y colóquela en FriendAssemblies.publickey:  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3. Muestre la clave pública almacenada en el archivo FriendAssemblies.publickey:  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. Cree un archivo de C# denominado `friend_signed_A` que incluya el siguiente código. El código usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para declarar friend_signed_B como un ensamblado de confianza.  
  
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
  
4. Compile y firme friend_signed_A mediante el siguiente comando.  
  
    ```csharp  
    csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    ```  
  
5. Cree un archivo de C# con el nombre `friend_signed_B` y que incluya el siguiente código. Dado que friend_signed_A especifica que friend_signed_B es un ensamblado de confianza, el código de friend_signed_B puede tener acceso a tipos `internal` y miembros de friend_signed_A. El archivo contiene el código siguiente.  
  
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
  
6. Compile y firme friend_signed_B mediante el siguiente comando.  
  
    ```csharp  
    csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    ```  
  
     El nombre del ensamblado generado por el compilador debe coincidir con el nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Debe especificar explícitamente el nombre del ensamblado de salida (.exe o .dll) mediante la opción `/out` del compilador.  Para obtener más información, consulte [/out (Opciones del compilador de C#)](../../../language-reference/compiler-options/out-compiler-option.md).  
  
7. Ejecute el archivo friend_signed_B.exe.  
  
     El programa imprime la cadena "Class1.Test".  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Existen similitudes entre el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> y la clase <xref:System.Security.Permissions.StrongNameIdentityPermission>. La diferencia principal es que <xref:System.Security.Permissions.StrongNameIdentityPermission> puede exigir permisos de seguridad para ejecutar una sección determinada de código, mientras el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controla la visibilidad de los miembros y tipos `internal`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Ensamblados de .NET](../../../../standard/assembly/index.md)
- [Ensamblados de confianza](../../../../standard/assembly/friend-assemblies.md)
- [Cómo: Crear ensamblados de confianza sin firmar (C#)](./how-to-create-unsigned-friend-assemblies.md)
- [/keyfile](../../../language-reference/compiler-options/keyfile-compiler-option.md)
- [Sn.exe (Herramienta de nombre seguro)](../../../../framework/tools/sn-exe-strong-name-tool.md)
- [Crear y utilizar ensamblados con nombre seguro](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md)
- [Guía de programación de C#](../../index.md)
