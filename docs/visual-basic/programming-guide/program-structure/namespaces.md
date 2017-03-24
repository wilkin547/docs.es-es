---
title: Espacios de nombres en Visual Basic | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.global
dev_langs:
- VB
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names, avoiding conflicts
- naming conflicts, namespaces
- namespaces, assemblies
- Visual Basic code, namespaces
- fully qualified names
- naming conventions, naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
caps.latest.revision: 27
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fe94e65ddbb4ebd2f7d26e8750a0a7ef5d3153af
ms.lasthandoff: 03/13/2017

---
# <a name="namespaces-in-visual-basic"></a>Espacios de nombres en Visual Basic
Los espacios de nombres organizan los objetos definidos en un ensamblado. Los ensamblados pueden contener varios espacios de nombres, que a su vez pueden contener otros espacios de nombres. Los espacios de nombres evitan las ambigüedades y simplifican las referencias cuando se usan grupos de objetos grandes, como las bibliotecas de clases.  
  
 Por ejemplo, el [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] define el <xref:System.Windows.Forms.ListBox>de clase en el <xref:System.Windows.Forms?displayProperty=fullName>espacio de nombres.</xref:System.Windows.Forms?displayProperty=fullName> </xref:System.Windows.Forms.ListBox> En el siguiente fragmento de código se muestra cómo declarar una variable con el nombre completo de esta clase:  
  
 [!code-vb[VbVbalrApplication Nº&6;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_1.vb)]  
  
## <a name="avoiding-name-collisions"></a>Evitar conflictos de nombres  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]espacios de nombres resuelven un problema que a veces denominado *corrupción de espacio de nombres*, en que el desarrollador de una biblioteca de clases está obstaculizado por el uso de nombres similares en otra biblioteca. Estos conflictos con componentes existentes a veces se denominan *conflictos de nombres*.  
  
 Por ejemplo, si crea una clase denominada `ListBox`, puede usarla en su proyecto sin ninguna calificación, Sin embargo, si desea utilizar el [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.Windows.Forms.ListBox>clase en el mismo proyecto, debe usar una referencia completa para sea única.</xref:System.Windows.Forms.ListBox> Si la referencia no es única, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] genera un error que indica que el nombre es ambiguo. En el ejemplo de código siguiente se muestra cómo declarar estos objetos:  
  
 [!code-vb[VbVbalrApplication&#7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_2.vb)]  
  
 En la siguiente ilustración se muestran dos jerarquías de espacio de nombres que contienen un objeto denominado `ListBox`.  
  
 ![Jerarquía de Namespace](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "vaNamespaceHierarchy")  
  
 De forma predeterminada, todos los archivos ejecutables que cree con [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] contienen un espacio de nombres con el mismo nombre que el proyecto. Por ejemplo, si define un objeto en un proyecto denominado `ListBoxProject`, el archivo ejecutable ListBoxProject.exe contiene un espacio de nombres llamado `ListBoxProject`.  
  
 Se puede usar el mismo espacio de nombres en varios ensamblados. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] los trata como un único conjunto de nombres. Por ejemplo, puede definir clases para un espacio de nombres (`SomeNameSpace`) en un ensamblado (`Assemb1`) y definir clases adicionales para el mismo espacio de nombres desde un ensamblado denominado `Assemb2`.  
  
## <a name="fully-qualified-names"></a>Nombres completos  
 Los nombres completos son referencias de objetos que llevan como prefijo el nombre del espacio de nombres en el que se define el objeto. Puede usar los objetos definidos en otros proyectos si crea una referencia a la clase (eligiendo **Agregar referencia** desde el menú **Proyecto** ) y usa el nombre completo del objeto en el código. En el siguiente fragmento de código se muestra cómo usar el nombre completo de un objeto desde el espacio de nombres de otro proyecto:  
  
 [!code-vb[VbVbalrApplication Nº&8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_3.vb)]  
  
 Los nombres completos evitan conflictos de nomenclatura, ya que permiten que el compilador determine el objeto que se está usando, aunque los nombres pueden llegar a ser largos y complicados. Para solucionar este problema, puede usar la instrucción `Imports` para definir un *alias*: un nombre abreviado que puede usar en lugar de un nombre completo. Por ejemplo, en el siguiente ejemplo de código se crean alias para dos nombres completos y se usan para definir dos objetos.  
  
 [!code-vb[VbVbalrApplication&#9;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_4.vb)]  
  
 [!code-vb[VbVbalrApplication&#10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_5.vb)]  
  
 Si usa la instrucción `Imports` sin un alias, puede usar todos los nombres de ese espacio de nombres sin ninguna calificación, siempre que sean únicos en el proyecto. Si el proyecto contiene instrucciones `Imports` de los espacios de nombres que contienen elementos con el mismo nombre, debe calificar totalmente ese nombre en el momento de usarlo. Supongamos, por ejemplo, que el proyecto contenía las dos instrucciones `Imports` siguientes:  
  
 [!code-vb[VbVbalrApplication&#11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_6.vb)]  
  
 Si intenta usar `Class1` sin calificarla por completo, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generará un error que indica que el nombre `Class1` es ambiguo.  
  
## <a name="namespace-level-statements"></a>Instrucciones de nivel de espacio de nombres  
 Dentro de un espacio de nombres, puede definir elementos tales como módulos, interfaces, clases, delegados, enumeraciones, estructuras y otros espacios de nombres. Los elementos tales como propiedades, procedimientos, variables y eventos no se pueden definir en el nivel de espacio de nombres. Estos elementos deben declararse dentro de contenedores tales como módulos, estructuras o clases.  
  
## <a name="global-keyword-in-fully-qualified-names"></a>Palabra clave Global en los nombres completos  
 Si ha definido una jerarquía anidada de espacios de nombres, código dentro de esa jerarquía podría tener acceso a la <xref:System?displayProperty=fullName>el espacio de nombres de .NET Framework.</xref:System?displayProperty=fullName> En el ejemplo siguiente se muestra una jerarquía en la que el `SpecialSpace.System` tener acceso los bloques de espacio de nombres <xref:System?displayProperty=fullName>.</xref:System?displayProperty=fullName>  
  
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
  
 Como resultado, el compilador de Visual Basic no puede resolver correctamente la referencia a <xref:System.Int32?displayProperty=fullName>, porque `SpecialSpace.System` no define `Int32`.</xref:System.Int32?displayProperty=fullName> Puede usar la palabra clave `Global` para iniciar la cadena de calificación en el nivel más externo de la biblioteca de clases de .NET Framework. Esto le permite especificar el <xref:System?displayProperty=fullName>espacio de nombres o cualquier otro espacio de nombres en la biblioteca de clases.</xref:System?displayProperty=fullName> Esto se ilustra en el siguiente ejemplo:  
  
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
  
 Puede usar `Global` para tener acceso a otros espacios de nombres de nivel de raíz, como <xref:Microsoft.VisualBasic?displayProperty=fullName>y cualquier espacio de nombres asociado a su proyecto.</xref:Microsoft.VisualBasic?displayProperty=fullName>  
  
## <a name="global-keyword-in-namespace-statements"></a>Palabra clave Global en las instrucciones de espacio de nombres  
 También puede utilizar el `Global` palabra clave en una [instrucción Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md). con lo que podrá definir un espacio de nombres fuera del espacio de nombres raíz del proyecto.  
  
 Todos los espacios de nombres del proyecto se basan en el espacio de nombres raíz de este.  Visual Studio asigna el nombre del proyecto como el espacio de nombres raíz predeterminado para todo el código del proyecto. Por ejemplo, si el proyecto se llama `ConsoleApplication1`, los respectivos elementos de programación pertenecerán al espacio de nombres `ConsoleApplication1`. Si declara `Namespace Magnetosphere`, las referencias a `Magnetosphere` en el proyecto tendrán acceso a `ConsoleApplication1.Magnetosphere`.  
  
 En los siguientes ejemplos se usa la palabra clave `Global` para declarar un espacio de nombres fuera del espacio de nombres raíz del proyecto.  
  
 [!code-vb[VbVbalrApplication&#22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_7.vb)]  
  
 En una declaración de espacio de nombres, no se puede anidar `Global` en otro espacio de nombres.  
  
 Puede usar el [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) para ver y modificar el **Root Namespace** del proyecto.  En cuanto a los proyectos nuevos, el **espacio de nombres raíz** tiene como nombre predeterminado el nombre del proyecto. Para que `Global` sea el espacio de nombres de nivel superior, puede borrar la entrada **Espacio de nombres raíz** para que el cuadro esté vacío. Si se borra **Espacio de nombres raíz** , ya no es necesario usar la palabra clave `Global` en las declaraciones de espacio de nombres.  
  
 Si una instrucción `Namespace` declara un nombre que también es un espacio de nombres en .NET Framework, el espacio de nombres de .NET Framework dejará de estar disponible si la palabra clave `Global` no se usa en un nombre completo. Para habilitar el acceso al espacio de nombres de .NET Framework sin usar la palabra clave `Global` , puede incluir la palabra clave `Global` en la instrucción `Namespace` .  
  
 En el siguiente ejemplo aparece la palabra clave `Global` en la declaración de espacio de nombres `System.Text` .  
  
 Si el `Global` palabra clave no estaba presente en la declaración de espacio de nombres, <xref:System.Text.StringBuilder>no se pudo acceder sin especificar `Global.System.Text.StringBuilder`.</xref:System.Text.StringBuilder> Para el proyecto `ConsoleApplication1`, las referencias a `System.Text` tendrían acceso a `ConsoleApplication1.System.Text` si no se usara la palabra clave `Global` .  
  
 [!code-vb[21 VbVbalrApplication](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_8.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ListBox></xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms?displayProperty=fullName></xref:System.Windows.Forms?displayProperty=fullName>   
 [Ensamblados y caché Global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Cómo: crear y utilizar ensamblados desde la línea de comandos](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)   
 [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Escribir código en soluciones de Office](https://msdn.microsoft.com/library/bb608596)
