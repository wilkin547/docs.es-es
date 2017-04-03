---
title: Ensamblados de confianza (C#) | Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ca01b9e91de08f3bdf53cd0572a3e1d1af0cf0af
ms.lasthandoff: 03/13/2017

---
# <a name="friend-assemblies-c"></a>Ensamblados de confianza (C#)
Un *ensamblado de confianza* puede acceder a los tipos y miembros [internal](../../../../csharp/language-reference/keywords/internal.md) de otro ensamblado. Si identifica un ensamblado como ensamblado de confianza, ya no hay que marcar los tipos y miembros como públicos para que otros ensamblados accedan a ellos. Esto resulta especialmente útil en los siguientes escenarios:  
  
-   Durante las pruebas unitarias, cuando se ejecuta código de prueba en un ensamblado independiente que requiere acceso a miembros del ensamblado en pruebas marcados como `internal`.  
  
-   Cuando desarrolla una biblioteca de clases y las adiciones a la biblioteca se incluyen en ensamblados independientes que requieren acceso a miembros de ensamblados existentes marcados como `internal`.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para identificar uno o más ensamblados de confianza en un ensamblado determinado. En el ejemplo siguiente se usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> en el ensamblado A y se especifica el ensamblado `AssemblyB` como ensamblado de confianza. Esto proporciona al ensamblado `AssemblyB` acceso a todos los tipos y miembros del ensamblado A marcados como `internal`.  
  
> [!NOTE]
>  Cuando se compila un ensamblado (ensamblado `AssemblyB`) que accederá a tipos o miembros internos de otro ensamblado (ensamblado *A*), hay que especificar explícitamente el nombre del archivo de salida (.exe o .dll) mediante la opción **/out** del compilador. Esto es necesario porque el compilador no ha generado aún el nombre del ensamblado que está creando en el momento en que se enlaza a referencias externas. Para obtener más información, consulte [/out (Opciones del compilador de C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).  
  
```csharp  
using System.Runtime.CompilerServices;  
using System;  
  
[assembly: InternalsVisibleTo("AssemblyB")]  
  
// The class is internal by default.  
class FriendClass  
{  
    public void Test()  
    {  
        Console.WriteLine("Sample Class");  
    }  
}  
  
// Public class that has an internal method.  
public class ClassWithFriendMethod  
{  
    internal void Test()  
    {  
        Console.WriteLine("Sample Method");  
    }  
  
}  
```  
  
 Solo los ensamblados que se especifiquen explícitamente como de confianza pueden acceder a tipos y miembros `internal`. Por ejemplo, si el ensamblado B es de confianza para el ensamblado A y el ensamblado C hace referencia al ensamblado B, C no tiene acceso a tipos `internal` en A.  
  
 El compilador realiza la validación básica del nombre de ensamblado de confianza pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Si el ensamblado *A* declara a *B* como ensamblado de confianza, las reglas de validación son las siguientes:  
  
-   Si el ensamblado *A* tiene un nombre seguro, el ensamblado *B* también deben tener un nombre seguro. El nombre de ensamblado de confianza que se pasa al atributo debe estar formado por el nombre del ensamblado y la clave pública de la clave de nombre seguro que se usa para firmar el ensamblado *B*.  
  
     El nombre de ensamblado de confianza que se pasa al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> no puede ser el nombre seguro del ensamblado *B*: no se incluyen la versión del ensamblado, la referencia cultural, la arquitectura o el token de clave pública.  
  
-   Si el ensamblado *A* no tiene nombre seguro, el nombre de ensamblado de confianza solo debe consistir en el nombre del ensamblado. Para obtener más información, vea [How to: Create Unsigned Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) (Cómo: Crear ensamblados de confianza no firmados [C#]).  
  
-   Si el ensamblado *B* tiene nombre seguro, hay que especificar la clave de nombre seguro del ensamblado *B* mediante la configuración del proyecto o la opción `/keyfile` de línea de comandos del compilador. Para obtener más información, vea [How to: Create Signed Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) (Cómo: Crear ensamblados de confianza firmados [C#]).  
  
 La clase <xref:System.Security.Permissions.StrongNameIdentityPermission> también ofrece la posibilidad de compartir tipos, con las siguientes diferencias:  
  
-   <xref:System.Security.Permissions.StrongNameIdentityPermission> se aplica a un tipo individual, mientras que un ensamblado de confianza se aplica a todo el ensamblado.  
  
-   Si hay cientos de tipos en el ensamblado *A* que quiere compartir con el ensamblado *B*, tiene que agregarles <xref:System.Security.Permissions.StrongNameIdentityPermission> a todos. Si usa un ensamblado de confianza, solo tiene que declarar una vez la relación de confianza.  
  
-   Si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, los tipos que quiera compartir han de declararse como públicos. Si usa un ensamblado de confianza, los tipos compartidos se declaran como `internal`.  
  
 Para obtener información sobre cómo acceder a los tipos y métodos `internal` de un ensamblado desde un archivo de módulo (un archivo con la extensión .netmodule), vea [/moduleassemblyname (C#)](../../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 <xref:System.Security.Permissions.StrongNameIdentityPermission>   
 [How to: Create Unsigned Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  (Cómo: Crear ensamblados de confianza no firmados [C#])  
 [How to: Create Signed Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  (Cómo: Crear ensamblados de confianza firmados [C#])  
 [Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  (Ensamblados y caché global de ensamblados [C#])  
 [Guía de programación de C#](../../../../csharp/programming-guide/index.md)
