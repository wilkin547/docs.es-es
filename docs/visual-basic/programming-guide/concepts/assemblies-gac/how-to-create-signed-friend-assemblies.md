---
title: "Cómo: crear ensamblados de confianza firmados (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
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
ms.openlocfilehash: 1a69f7e833800ec7417bc35fad763f1001b3e7f9
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a>Cómo: crear ensamblados de confianza firmados (Visual Basic)
Este ejemplo muestra cómo utilizar los ensamblados de confianza con ensamblados que tienen nombres seguros. Ambos ensamblados deben tener nombres seguros. Aunque ambos ensamblados en este ejemplo utilizan las mismas claves, puede usar claves diferentes para dos ensamblados.  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a>Para crear un ensamblado firmado y un ensamblado de confianza  
  
1.  Abra un símbolo del sistema.  
  
2.  Utilice la siguiente secuencia de comandos con la herramienta nombre seguro para generar un archivo de claves y mostrar su clave pública. Para obtener más información, vea [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).  
  
    1.  Generar una clave de nombre seguro para este ejemplo y almacenarla en el archivo FriendAssemblies.snk:  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  Extraer la clave pública de FriendAssemblies.snk y colóquela en FriendAssemblies.publickey:  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  Mostrar la clave pública almacenada en el archivo FriendAssemblies.publickey:  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  Cree un archivo de Visual Basic llamado `friend_signed_A` que contiene el código siguiente. El código usa el <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>atributo declarar friend_signed_B como un ensamblado de confianza.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
  
     La herramienta de nombre seguro genera una nueva clave pública cada vez que se ejecuta. Por lo tanto, debe reemplazar la clave pública en el código siguiente con la clave pública que acaba de generar, como se muestra en el ejemplo siguiente.  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    Imports System.Runtime.CompilerServices  
  
    <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>   
    Public Class Class1  
        Public Sub Test()  
            System.Console.WriteLine("Class1.Test")  
            System.Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
4.  Compile y firme friend_signed_A mediante el siguiente comando.  
  
    ```vb  
    Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  Crear un archivo de Visual Basic que se denomina `friend_signed_B` y contiene el código siguiente. Dado que friend_signed_A especifica que friend_signed_B es un ensamblado de confianza, puede tener acceso el código de friend_signed_B `Friend` tipos y miembros de friend_signed_A. El archivo contiene el código siguiente.  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6.  Compile y firme friend_signed_B mediante el siguiente comando.  
  
    ```vb  
    Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     El nombre del ensamblado generado por el compilador debe coincidir con el nombre de ensamblado de confianza pasado a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>atributo.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Puede establecer explícitamente el ensamblado utilizando el `/out` opción del compilador. Para obtener más información, consulte [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
7.  Ejecute el archivo friend_signed_B.exe.  
  
     El programa imprime la cadena "Class1.Test".  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Hay similitudes entre el <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>atributo y la <xref:System.Security.Permissions.StrongNameIdentityPermission>clase.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> La principal diferencia es que <xref:System.Security.Permissions.StrongNameIdentityPermission>puede solicitar permisos de seguridad para ejecutar una sección concreta del código, mientras que el <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>atributo controla la visibilidad de `Friend` tipos y miembros.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 [Ensamblados y caché Global de ensamblados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Friend (ensamblados) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)   
 [Cómo: crear ensamblados de confianza sin firmar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)   
 [/ keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [Sn.exe (herramienta de nombre seguro)](https://msdn.microsoft.com/library/k5b5tt23)   
 [Crear y utilizar ensamblados con nombre seguro](https://msdn.microsoft.com/library/xwb8f617)   
 [Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md)
