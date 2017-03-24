---
title: "Cómo: crear ensamblados de confianza sin firmar (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ceddb35c306f72c8927deda326d9fcca6c75d786
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a>Cómo: crear ensamblados de confianza sin firmar (Visual Basic)
Este ejemplo muestra cómo utilizar los ensamblados de confianza con ensamblados no firmados.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>Para crear un ensamblado y un ensamblado de confianza  
  
1.  Abra un símbolo del sistema.  
  
2.  Cree un archivo de Visual Basic llamado `friend_signed_A.` que contiene el código siguiente. El código usa el <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>atributo declarar friend_signed_B como un ensamblado de confianza.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
  
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
  
4.  Cree un archivo de Visual Basic llamado `friend_unsigned_B` que contiene el código siguiente. Dado que friend_unsigned_A especifica que friend_unsigned_B es un ensamblado de confianza, puede tener acceso el código de friend_unsigned_B `Friend` tipos y miembros de friend_unsigned_A.  
  
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
  
     El nombre del ensamblado generado por el compilador debe coincidir con el nombre de ensamblado de confianza que se pasa a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>atributo.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Puede establecer explícitamente el ensamblado utilizando el `/out` opción del compilador.  
  
6.  Ejecute el archivo friend_signed_B.exe.  
  
     El programa imprime dos cadenas: "Class1.Test" y "Class2.Test".  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Hay similitudes entre el <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>atributo y la <xref:System.Security.Permissions.StrongNameIdentityPermission>clase.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> La principal diferencia es que <xref:System.Security.Permissions.StrongNameIdentityPermission>puede solicitar permisos de seguridad para ejecutar una sección concreta del código, mientras que el <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>atributo controla la visibilidad de `Friend` tipos y miembros.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 [Ensamblados y caché Global de ensamblados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Friend (ensamblados) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)   
 [Cómo: crear ensamblados de confianza firmados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)   
 [Conceptos de la Guía de programación](../../../../visual-basic/programming-guide/concepts/index.md)
