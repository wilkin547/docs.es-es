---
title: Ensamblados de confianza (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d3a37629582e4fc2606afaf606735464c0d247a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="friend-assemblies-visual-basic"></a>Ensamblados de confianza (Visual Basic)
A *ensamblado de confianza* es un ensamblado que puede tener acceso a otro ensamblado [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) tipos y miembros. Si identifica un ensamblado como ensamblado de confianza, ya no hay que marcar los tipos y miembros como públicos para que otros ensamblados accedan a ellos. Esto resulta especialmente útil en los siguientes escenarios:  
  
-   Durante las pruebas unitarias, cuando se ejecuta el código de prueba un ensamblado independiente pero requiere acceso a los miembros del ensamblado que se está probando que están marcados como `Friend`.  
  
-   Cuando está desarrollando una biblioteca de clases y las adiciones a la biblioteca de contienen en ensamblados independientes pero requieren acceso a los miembros de los ensamblados existentes que están marcados como `Friend`.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para identificar uno o más ensamblados de confianza para un ensamblado determinado. En el ejemplo siguiente se usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> en el ensamblado A y se especifica el ensamblado `AssemblyB` como un ensamblado de confianza. Esto proporciona al ensamblado `AssemblyB` acceso a todos los tipos y miembros del ensamblado A marcados como `Friend`.  
  
> [!NOTE]
>  Cuando se compila un ensamblado (ensamblado `AssemblyB`) que accederá a tipos o miembros internos de otro ensamblado (ensamblado *A*), hay que especificar explícitamente el nombre del archivo de salida (.exe o .dll) mediante la opción **/out** del compilador. Esto es necesario porque el compilador no ha generado aún el nombre del ensamblado que está creando en el momento en que se enlaza a referencias externas. Para obtener más información, consulte [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports System  
<Assembly: InternalsVisibleTo("AssemblyB")>   
  
' Friend class.  
Friend Class FriendClass  
    Public Sub Test()  
        Console.WriteLine("Sample Class")  
    End Sub  
End Class  
  
' Public class with a Friend method.  
Public Class ClassWithFriendMethod  
    Friend Sub Test()  
        Console.WriteLine("Sample Method")  
    End Sub  
End Class  
```  
  
 Solo los ensamblados que se especifiquen explícitamente como de confianza pueden acceder a tipos y miembros `Friend`. Por ejemplo, si el ensamblado B es de confianza para el ensamblado A y el ensamblado C hace referencia al ensamblado B, C no tiene acceso a tipos `Friend` en A.  
  
 El compilador realiza una validación básica del nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Si el ensamblado *A* declara a *B* como ensamblado de confianza, las reglas de validación son las siguientes:  
  
-   Si el ensamblado *A* tiene un nombre seguro, el ensamblado *B* también deben tener un nombre seguro. El nombre de ensamblado de confianza que se pasa al atributo debe estar formado por el nombre del ensamblado y la clave pública de la clave de nombre seguro que se usa para firmar el ensamblado *B*.  
  
     El nombre de ensamblado de confianza que se pasa al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> no puede ser el nombre seguro del ensamblado *B*: no se incluyen la versión del ensamblado, la referencia cultural, la arquitectura o el token de clave pública.  
  
-   Si el ensamblado *A* no tiene nombre seguro, el nombre de ensamblado de confianza solo debe consistir en el nombre del ensamblado. Para obtener más información, consulte [Cómo: crear ensamblados de confianza sin signo (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).  
  
-   Si el ensamblado *B* tiene nombre seguro, hay que especificar la clave de nombre seguro del ensamblado *B* mediante la configuración del proyecto o la opción `/keyfile` de línea de comandos del compilador. Para obtener más información, consulte [Cómo: crear ensamblados firmados de confianza (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).  
  
 La clase <xref:System.Security.Permissions.StrongNameIdentityPermission> también proporciona la capacidad de compartir tipos, con las siguientes diferencias:  
  
-   <xref:System.Security.Permissions.StrongNameIdentityPermission> se aplica a un tipo individual, mientras que un ensamblado de confianza se aplica al ensamblado completo.  
  
-   Si hay cientos de tipos en el ensamblado *A* que quiere compartir con el ensamblado *B*, tiene que agregarles <xref:System.Security.Permissions.StrongNameIdentityPermission> a todos. Si usa un ensamblado de confianza, solo tiene que declarar una vez la relación de confianza.  
  
-   Si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, los tipos que quiere compartir tienen que declararse como públicos. Si usa un ensamblado de confianza, los tipos compartidos se declaran como `Friend`.  
  
 Para obtener información sobre cómo obtener acceso a un ensamblado `Friend` tipos y métodos de un archivo de módulo (archivo con la extensión de archivo .netmodule), consulte [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 <xref:System.Security.Permissions.StrongNameIdentityPermission>  
 [Cómo: crear ensamblados de confianza sin firmar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [Cómo: crear ensamblados de confianza firmados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [Ensamblados y caché global de ensamblados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md)
