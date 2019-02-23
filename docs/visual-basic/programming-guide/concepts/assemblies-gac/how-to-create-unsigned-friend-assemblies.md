---
title: Filtrar Crear ensamblados de confianza sin firmar (Visual Basic)
ms.date: 03/14/2018
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
ms.openlocfilehash: 8c1d5fb24d0032e88b951eefa1bd7a3a8c6ccb88
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748133"
---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a>Filtrar Crear ensamblados de confianza sin firmar (Visual Basic)
En este ejemplo se muestra cómo usar ensamblados de confianza con ensamblados sin firmar.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>Para crear un ensamblado y un ensamblado de confianza  
  
1.  Abra un símbolo del sistema.  
  
2.  Cree un archivo de Visual Basic llamado `friend_signed_A.` que contiene el código siguiente. El código usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para declarar friend_signed_B como un ensamblado de confianza.  
  
    ```vb  
    ' friend_unsigned_A.vb  
    ' Compile with:   
    ' vbc -target:library friend_unsigned_A.vb  
    Imports System.Runtime.CompilerServices  
    Imports System  
  
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
  
3.  Compile y firme friend_signed_A mediante el siguiente comando.  
  
    ```console  
    vbc -target:library friend_unsigned_A.vb  
    ```  
  
4.  Cree un archivo de Visual Basic llamado `friend_unsigned_B` que contiene el código siguiente. Como friend_unsigned_A especifica que friend_unsigned_B es un ensamblado de confianza, el código de friend_unsigned_B puede tener acceso a tipos `Friend` y miembros de friend_unsigned_A.  
  
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
  
5.  Compile friend_signed_B mediante el siguiente comando.  
  
    ```console
    vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     El nombre del ensamblado que genera el compilador debe coincidir con el nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Puede establecer explícitamente el ensamblado utilizando el `/out` opción del compilador.  
  
6.  Ejecute el archivo friend_signed_B.exe.  
  
     El programa muestra dos cadenas: "Class1.Test" y "Class2.Test".  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Existen similitudes entre el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> y la clase <xref:System.Security.Permissions.StrongNameIdentityPermission>. La diferencia principal es que <xref:System.Security.Permissions.StrongNameIdentityPermission> puede exigir permisos de seguridad para ejecutar una sección determinada de código, mientras el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controla la visibilidad de los miembros y tipos `Friend`.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Ensamblados de .NET](../../../../standard/assembly/index.md)
- [Ensamblados de confianza (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)
- [Cómo: Crear ensamblados de confianza firmados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [Conceptos de la Guía de programación](../../../../visual-basic/programming-guide/concepts/index.md)
