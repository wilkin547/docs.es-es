---
title: Friend (ensamblados) (Visual Basic) | Documentos de Microsoft
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
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c6e01ae91b9d5d875bb618993cd9eda82db59399
ms.lasthandoff: 03/13/2017

---
# <a name="friend-assemblies-visual-basic"></a>Friend (ensamblados) (Visual Basic)
Un *un ensamblado de confianza* es un ensamblado que puede tener acceso a otro ensamblado [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) tipos y miembros. Si se identifica un ensamblado como ensamblado de confianza, ya no se debe marcar tipos y miembros como public puedan tener acceso a otros ensamblados. Esto resulta especialmente útil en los escenarios siguientes:  
  
-   Durante las pruebas unitarias, cuando se ejecuta el código de prueba en un ensamblado independiente pero requiere acceso a los miembros del ensamblado que se está probando se marcan como `Friend`.  
  
-   Cuando está desarrollando una biblioteca de clases y las adiciones a la biblioteca de contienen en ensamblados independientes pero requieren acceso a los miembros de ensamblados existentes que están marcados como `Friend`.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>atributo para identificar uno o varios ensamblados de confianza para un ensamblado determinado.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> En el ejemplo siguiente se utiliza la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>de atributo en el ensamblado A y especifica el ensamblado `AssemblyB` como un ensamblado de confianza.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Esto proporciona el ensamblado `AssemblyB` acceso a todos los tipos y miembros del ensamblado que están marcados como `Friend`.  
  
> [!NOTE]
>  Cuando se compila un ensamblado (ensamblado `AssemblyB`) que tendrá acceso a tipos o miembros internos de otro ensamblado (ensamblado *A*), debe especificar explícitamente el nombre del archivo de salida (.exe o .dll) mediante la **/out** opción del compilador. Esto es necesario porque el compilador no ha generado aún el nombre del ensamblado que está creando en el momento de enlazar a las referencias externas. Para obtener más información, consulte [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
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
  
 Solo los ensamblados que se especifiquen explícitamente como se pueden tener acceso sus amigos `Friend` tipos y miembros. Por ejemplo, si el ensamblado B es un amigo assembly A y el ensamblado C hace referencia al ensamblado B, C no tiene acceso a `Friend` tipos en A.  
  
 El compilador realiza la validación básica del nombre del ensamblado de confianza pasado a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>atributo.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Si ensamblado *A* declara *B* como un ensamblado de confianza, las reglas de validación son los siguientes:  
  
-   Si ensamblado *A* tiene un nombre de ensamblado seguro *B* también deben tener nombres seguros. El nombre de ensamblado de confianza que se pasa al atributo debe consistir en el nombre del ensamblado y la clave pública de la clave de nombre seguro que se utiliza para firmar el ensamblado *B*.  
  
     El nombre de ensamblado de confianza que se pasa a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>atributo no puede ser el nombre seguro del ensamblado *B*: no se incluyen la versión del ensamblado, la referencia cultural, la arquitectura o el token de clave pública.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
  
-   Si ensamblado *A* no es segura con nombre, el nombre de ensamblado de confianza debe consistir sólo el nombre del ensamblado. Para obtener más información, consulte [Cómo: crear ensamblados de confianza sin firmar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).  
  
-   Si ensamblado *B* tiene un nombre seguro, debe especificar la clave de nombre seguro del ensamblado *B* mediante la configuración del proyecto o la línea de comandos `/keyfile` opción del compilador. Para obtener más información, consulte [Cómo: crear ensamblados firmados de confianza (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).  
  
 La <xref:System.Security.Permissions.StrongNameIdentityPermission>clase también proporciona la capacidad de compartir tipos, con las siguientes diferencias:</xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
-   <xref:System.Security.Permissions.StrongNameIdentityPermission>se aplica a un tipo individual, mientras que un ensamblado de confianza se aplica a todo el ensamblado.</xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
-   Si hay cientos de tipos en el ensamblado *A* que desea compartir con el ensamblado *B*, tendrá que agregar <xref:System.Security.Permissions.StrongNameIdentityPermission>a todos ellos.</xref:System.Security.Permissions.StrongNameIdentityPermission> Si utiliza un ensamblado de confianza, solo debe declarar la relación de confianza una vez.  
  
-   Si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, los tipos que desea compartir deben declararse como públicos.</xref:System.Security.Permissions.StrongNameIdentityPermission> Si utiliza un ensamblado de confianza, los tipos compartidos se declaran como `Friend`.  
  
 Para obtener información sobre cómo obtener acceso a un ensamblado `Friend` tipos y métodos de un archivo de módulo (archivo con la extensión .netmodule), consulte [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 <xref:System.Security.Permissions.StrongNameIdentityPermission></xref:System.Security.Permissions.StrongNameIdentityPermission>   
 [Cómo: crear ensamblados de confianza sin firmar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)   
 [Cómo: crear ensamblados de confianza firmados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)   
 [Ensamblados y caché Global de ensamblados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md)
