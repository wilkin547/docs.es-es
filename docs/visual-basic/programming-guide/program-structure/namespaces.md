---
title: Espacios de nombres
ms.date: 07/20/2015
f1_keywords:
- vb.global
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names [Visual Basic], avoiding conflicts
- naming conflicts [Visual Basic], namespaces
- namespaces [Visual Basic], assemblies
- Visual Basic code, namespaces
- fully qualified names [Visual Basic]
- naming conventions [Visual Basic], naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
ms.openlocfilehash: f4521fa10c3bb9e8e121e3c228a23061becd1741
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072202"
---
# <a name="namespaces-in-visual-basic"></a>Espacios de nombres en Visual Basic

Los espacios de nombres organizan los objetos definidos en un ensamblado. Los ensamblados pueden contener varios espacios de nombres, que a su vez pueden contener otros espacios de nombres. Los espacios de nombres evitan las ambigüedades y simplifican las referencias cuando se usan grupos de objetos grandes, como las bibliotecas de clases.  
  
 Por ejemplo, el .NET Framework define la <xref:System.Windows.Forms.ListBox> clase en el <xref:System.Windows.Forms?displayProperty=nameWithType> espacio de nombres. En el siguiente fragmento de código se muestra cómo declarar una variable con el nombre completo de esta clase:  
  
 [!code-vb[VbVbalrApplication#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#6)]  
  
## <a name="avoiding-name-collisions"></a>Evitar conflictos de nombres  

 .NET Framework espacios de nombres resuelven un problema que a veces se denomina *contaminación de espacio de nombres*, en el que el desarrollador de una biblioteca de clases se ve obstaculizado por el uso de nombres similares en otra biblioteca. Estos conflictos con componentes existentes a veces se denominan *conflictos de nombres*.  
  
 Por ejemplo, si crea una clase denominada `ListBox`, puede usarla en su proyecto sin ninguna calificación, Sin embargo, si desea utilizar la clase .NET Framework <xref:System.Windows.Forms.ListBox> en el mismo proyecto, debe usar una referencia completa para que la referencia sea única. Si la referencia no es única, Visual Basic genera un error que indica que el nombre es ambiguo. En el ejemplo de código siguiente se muestra cómo declarar estos objetos:  
  
 [!code-vb[VbVbalrApplication#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#7)]  
  
 En la ilustración siguiente se muestran dos jerarquías de espacios de nombres que contienen un objeto denominado `ListBox` :  
  
 ![Captura de pantalla que muestra dos jerarquías de espacios de nombres.](./media/namespaces/visual-basic-namespace-hierarchy.gif)  
  
 De forma predeterminada, cada archivo ejecutable que se crea con Visual Basic contiene un espacio de nombres con el mismo nombre que el proyecto. Por ejemplo, si define un objeto en un proyecto denominado `ListBoxProject`, el archivo ejecutable ListBoxProject.exe contiene un espacio de nombres llamado `ListBoxProject`.  
  
 Se puede usar el mismo espacio de nombres en varios ensamblados. Visual Basic los trata como un único conjunto de nombres. Por ejemplo, puede definir clases para un espacio de nombres ( `SomeNameSpace` ) en un ensamblado ( `Assemb1`) y definir clases adicionales para el mismo espacio de nombres desde un ensamblado denominado `Assemb2`.  
  
## <a name="fully-qualified-names"></a>nombres completos  

 Los nombres completos son referencias de objetos que llevan como prefijo el nombre del espacio de nombres en el que se define el objeto. Puede usar los objetos definidos en otros proyectos si crea una referencia a la clase (eligiendo **Agregar referencia** desde el menú **Proyecto** ) y usa el nombre completo del objeto en el código. En el siguiente fragmento de código se muestra cómo usar el nombre completo de un objeto desde el espacio de nombres de otro proyecto:  
  
 [!code-vb[VbVbalrApplication#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#8)]  
  
 Los nombres completos evitan conflictos de nomenclatura, ya que permiten que el compilador determine el objeto que se está usando, aunque los nombres pueden llegar a ser largos y complicados. Para solucionar este problema, puede usar la instrucción `Imports` para definir un *alias*: un nombre abreviado que puede usar en lugar de un nombre completo. Por ejemplo, en el siguiente ejemplo de código se crean alias para dos nombres completos y se usan para definir dos objetos.  
  
 [!code-vb[VbVbalrApplication#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#9)]  
  
 [!code-vb[VbVbalrApplication#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#10)]  
  
 Si usa la instrucción `Imports` sin un alias, puede usar todos los nombres de ese espacio de nombres sin ninguna calificación, siempre que sean únicos en el proyecto. Si el proyecto contiene instrucciones `Imports` de los espacios de nombres que contienen elementos con el mismo nombre, debe calificar totalmente ese nombre en el momento de usarlo. Supongamos, por ejemplo, que el proyecto contenía las dos instrucciones `Imports` siguientes:  
  
 [!code-vb[VbVbalrApplication#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#11)]  
  
 Si intenta usar `Class1` sin calificarla por completo, Visual Basic genera un error que indica que el nombre `Class1` es ambiguo.  
  
## <a name="namespace-level-statements"></a>Instrucciones de nivel de espacio de nombres  

 Dentro de un espacio de nombres, puede definir elementos tales como módulos, interfaces, clases, delegados, enumeraciones, estructuras y otros espacios de nombres. Los elementos tales como propiedades, procedimientos, variables y eventos no se pueden definir en el nivel de espacio de nombres. Estos elementos deben declararse dentro de contenedores tales como módulos, estructuras o clases.  
  
## <a name="global-keyword-in-fully-qualified-names"></a>Palabra clave Global en los nombres completos  

 Si ha definido una jerarquía anidada de espacios de nombres, el código insertado en esa jerarquía podría tener bloqueado el acceso al espacio de nombres <xref:System?displayProperty=nameWithType> de .NET Framework. En el siguiente ejemplo se muestra una jerarquía en la que el espacio de nombres `SpecialSpace.System` bloquea el acceso a <xref:System?displayProperty=nameWithType>.  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As System.Int32  
                Dim n As System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 Como resultado, el compilador de Visual Basic no puede resolver correctamente la referencia a <xref:System.Int32?displayProperty=nameWithType>, porque `SpecialSpace.System` no define `Int32`. Puede usar la palabra clave `Global` para iniciar la cadena de calificación en el nivel más externo de la biblioteca de clases de .NET Framework. De este modo, puede especificar el espacio de nombres <xref:System?displayProperty=nameWithType> o cualquier otro espacio de nombres en la biblioteca de clases. Esto se ilustra en el siguiente ejemplo:  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As Global.System.Int32  
                Dim n As Global.System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 Puede usar `Global` para obtener acceso a otros espacios de nombres de nivel de raíz, como <xref:Microsoft.VisualBasic?displayProperty=nameWithType>, y a cualquier espacio de nombres asociado a su proyecto.  
  
## <a name="global-keyword-in-namespace-statements"></a>Palabra clave Global en las instrucciones de espacio de nombres  

 También puede usar la palabra clave `Global` en una [Namespace Statement](../../language-reference/statements/namespace-statement.md). con lo que podrá definir un espacio de nombres fuera del espacio de nombres raíz del proyecto.  
  
 Todos los espacios de nombres del proyecto se basan en el espacio de nombres raíz de este.  Visual Studio asigna el nombre del proyecto como el espacio de nombres raíz predeterminado para todo el código del proyecto. Por ejemplo, si el proyecto se llama `ConsoleApplication1`, los respectivos elementos de programación pertenecerán al espacio de nombres `ConsoleApplication1`. Si declara `Namespace Magnetosphere`, las referencias a `Magnetosphere` en el proyecto tendrán acceso a `ConsoleApplication1.Magnetosphere`.  
  
 En los siguientes ejemplos se usa la palabra clave `Global` para declarar un espacio de nombres fuera del espacio de nombres raíz del proyecto.  
  
 [!code-vb[VbVbalrApplication#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#22)]  
  
 En una declaración de espacio de nombres, no se puede anidar `Global` en otro espacio de nombres.  
  
 Puede usar la [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) para ver y modificar el **espacio de nombres raíz** del proyecto.  En cuanto a los proyectos nuevos, el **espacio de nombres raíz** tiene como nombre predeterminado el nombre del proyecto. Para que `Global` sea el espacio de nombres de nivel superior, puede borrar la entrada **Espacio de nombres raíz** para que el cuadro esté vacío. Si se borra **Espacio de nombres raíz** , ya no es necesario usar la palabra clave `Global` en las declaraciones de espacio de nombres.  
  
 Si una instrucción `Namespace` declara un nombre que también es un espacio de nombres en .NET Framework, el espacio de nombres de .NET Framework dejará de estar disponible si la palabra clave `Global` no se usa en un nombre completo. Para habilitar el acceso al espacio de nombres de .NET Framework sin usar la palabra clave `Global` , puede incluir la palabra clave `Global` en la instrucción `Namespace` .  
  
 En el siguiente ejemplo aparece la palabra clave `Global` en la declaración de espacio de nombres `System.Text` .  
  
 Si la palabra clave `Global` no estuviera presente en la declaración de espacio de nombres, no se podría obtener acceso a <xref:System.Text.StringBuilder> sin especificar `Global.System.Text.StringBuilder`. Para el proyecto `ConsoleApplication1`, las referencias a `System.Text` tendrían acceso a `ConsoleApplication1.System.Text` si no se usara la palabra clave `Global` .  
  
 [!code-vb[VbVbalrApplication#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#21)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms?displayProperty=nameWithType>
- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Referencias y la instrucción Imports](references-and-the-imports-statement.md)
- [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Escribir código en soluciones de Office](/visualstudio/vsto/writing-code-in-office-solutions)
