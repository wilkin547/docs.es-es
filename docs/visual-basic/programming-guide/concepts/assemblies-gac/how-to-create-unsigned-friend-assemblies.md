---
title: "Cómo: crear ensamblados de confianza sin firmar (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a2b2667c60a07a2897a0934d210901042e2e43c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a>Cómo: crear ensamblados de confianza sin firmar (Visual Basic)
En este ejemplo se muestra cómo usar ensamblados de confianza con ensamblados sin firmar.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>Para crear un ensamblado y un ensamblado de confianza  
  
1.  Abra un símbolo del sistema.  
  
2.  Cree un archivo de Visual Basic denominado `friend_signed_A.` que contiene el código siguiente. El código usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para declarar friend_signed_B como un ensamblado de confianza.  
  
    ```vb  
    ' friend_unsigned_A.vb  
    ' Compile with:   
    ' Vbc /target:library friend_unsigned_A.vb  
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
  
    ```vb  
    Vbc /target:library friend_unsigned_A.vb  
    ```  
  
4.  Cree un archivo de Visual Basic denominado `friend_unsigned_B` que contiene el código siguiente. Como friend_unsigned_A especifica que friend_unsigned_B es un ensamblado de confianza, el código de friend_unsigned_B puede tener acceso a tipos `Friend` y miembros de friend_unsigned_A.  
  
    ```vb  
    ' friend_unsigned_B.vb  
    ' Compile with:   
    ' Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
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
  
    ```vb  
    Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     El nombre del ensamblado que genera el compilador debe coincidir con el nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Puede establecer explícitamente el ensamblado utilizando el `/out` opción del compilador.  
  
6.  Ejecute el archivo friend_signed_B.exe.  
  
     El programa imprime dos cadenas: "Class1.Test" y "Class2.Test".  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Existen similitudes entre el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> y la clase <xref:System.Security.Permissions.StrongNameIdentityPermission>. La diferencia principal es que <xref:System.Security.Permissions.StrongNameIdentityPermission> puede exigir permisos de seguridad para ejecutar una sección determinada de código, mientras el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controla la visibilidad de los miembros y tipos `Friend`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [Ensamblados y caché global de ensamblados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Ensamblados de confianza (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [Cómo: crear ensamblados de confianza firmados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [Conceptos de la Guía de programación](../../../../visual-basic/programming-guide/concepts/index.md)
