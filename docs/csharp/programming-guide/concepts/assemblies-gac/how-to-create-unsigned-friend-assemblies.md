---
title: Procedimiento Crear ensamblados de confianza sin firmar (C#)
ms.date: 07/20/2015
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
ms.openlocfilehash: 6bc2d807b3d1cf6c82a9ba6303139b9758581f35
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318239"
---
# <a name="how-to-create-unsigned-friend-assemblies-c"></a>Procedimiento Crear ensamblados de confianza sin firmar (C#)
En este ejemplo se muestra cómo usar ensamblados de confianza con ensamblados sin firmar.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>Para crear un ensamblado y un ensamblado de confianza  
  
1. Abra un símbolo del sistema.  
  
2. Cree un archivo de C# denominado `friend_unsigned_A.` que incluya el siguiente código. El código usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para declarar friend_unsigned_B como un ensamblado de confianza.  
  
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
  
3. Compile y firme friend_unsigned_A mediante el siguiente comando.  
  
    ```csharp  
    csc /target:library friend_unsigned_A.cs  
    ```  
  
4. Cree un archivo de C# denominado `friend_unsigned_B` que incluya el siguiente código. Como friend_unsigned_A especifica que friend_unsigned_B es un ensamblado de confianza, el código de friend_unsigned_B puede tener acceso a tipos `internal` y miembros de friend_unsigned_A.  
  
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
  
5. Compile friend_unsigned_B mediante el siguiente comando.  
  
    ```csharp  
    csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs  
    ```  
  
     El nombre del ensamblado que genera el compilador debe coincidir con el nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Debe especificar explícitamente el nombre del ensamblado de salida (.exe o .dll) mediante la opción `/out` del compilador. Para obtener más información, consulte [/out (Opciones del compilador de C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).  
  
6. Ejecute el archivo friend_unsigned_B.exe.  
  
     El programa imprime dos cadenas: "Class1.Test" y "Class2.Test".  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Existen similitudes entre el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> y la clase <xref:System.Security.Permissions.StrongNameIdentityPermission>. La diferencia principal es que <xref:System.Security.Permissions.StrongNameIdentityPermission> puede exigir permisos de seguridad para ejecutar una sección determinada de código, mientras el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controla la visibilidad de los miembros y tipos `internal`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Ensamblados de .NET](../../../../standard/assembly/index.md)
- [Ensamblados de confianza](../../../../standard/assembly/friend-assemblies.md)
- [Procedimiento para crear ensamblados de confianza firmados (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [Guía de programación de C#](../../../../csharp/programming-guide/index.md)
