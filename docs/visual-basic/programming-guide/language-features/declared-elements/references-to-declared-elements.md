---
title: Referencias a elementos declarados (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements
- references, declared elements
- qualified names
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 48a04f81075accc073b0d1f5b7a61006bef807ae
ms.lasthandoff: 03/13/2017

---
# <a name="references-to-declared-elements-visual-basic"></a>Referencias a elementos declarados (Visual Basic)
Cuando el código hace referencia a un elemento declarado, el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador coincide con el nombre de la referencia con la declaración pertinente del nombre. Si más de un elemento se declara con el mismo nombre, puede controlar cuáles de esos elementos se haga referencia a *calificación* su nombre.  
  
 El compilador intenta hacer coincidir una referencia de nombre con una declaración de nombre con el *ámbito más restringido*. Esto significa que comienza con el código que hace la referencia y se mueve hacia afuera a través de los niveles sucesivos de elementos contenedores.  
  
 El ejemplo siguiente muestra las referencias a dos variables con el mismo nombre. En el ejemplo se declara dos variables, cada uno denominado `totalCount`, en diferentes niveles de ámbito en el módulo `container`. Cuando el procedimiento `showCount` muestra `totalCount` sin calificación, el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador resuelve la referencia a la declaración con el ámbito más restringido, concretamente la declaración local dentro de `showCount`. Cuando califica `totalCount` con el módulo contenedor `container`, el compilador resuelve la referencia a la declaración con el ámbito más amplio.  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a>Calificar un nombre de elemento  
 Si desea invalidar este proceso de búsqueda y especificar un nombre declarado en un ámbito más amplio, debe *calificar* el nombre con el elemento contenedor del ámbito más amplio. En algunos casos, es posible que deba calificar el elemento contenedor.  
  
 Calificar un nombre significa que precede en la instrucción de origen con la información que identifica dónde se define el elemento de destino. Esta información se denomina un *cadena de calificación*. Puede incluir uno o más espacios de nombres y un módulo, clase o estructura.  
  
 La cadena de calificación debe especificar de forma inequívoca el módulo, clase o estructura que contiene el elemento de destino. El contenedor a su vez puede estar ubicado en otro elemento contenedor, normalmente un espacio de nombres. Debe incluir varios elementos contenedores en la cadena de calificación.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Para obtener acceso a un elemento declarado mediante la calificación de su nombre  
  
1.  Determinar la ubicación en la que se ha definido el elemento. Esto puede incluir un espacio de nombres o incluso una jerarquía de espacios de nombres. En el espacio de nombres de nivel inferior, el elemento debe estar contenido en un módulo, clase o estructura.  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2.  Determinar una ruta de acceso de calificación basada en la ubicación del elemento de destino. Comience con el espacio de nombres de nivel superior, continúe con el espacio de nombres de nivel más bajo y termina con el módulo, clase o estructura que contiene el elemento de destino. Cada elemento de la ruta de acceso debe contener el elemento que le sigue.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3.  Prepare la cadena de calificación para el elemento de destino. Coloque un punto (`.`) después de cada elemento de la ruta de acceso. La aplicación debe tener acceso a cada elemento de la cadena de calificación.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  Escriba la expresión o instrucción de asignación que hace referencia al elemento de destino de la manera normal.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  Delante del nombre del elemento de destino con la cadena de calificación. El nombre debe seguir inmediatamente el período (`.`) que sigue el módulo, clase o estructura que contiene el elemento.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  El compilador utiliza la cadena de calificación para encontrar una declaración clara e inequívoca a la que puede coincidir con la referencia de elemento de destino.  
  
 También podría tener que calificar una referencia de nombre si su aplicación tiene acceso a más de un elemento de programación que tiene el mismo nombre. Por ejemplo, el <xref:System.Windows.Forms>y <xref:System.Web.UI.WebControls>espacios de nombres contienen un `Label` clase (<xref:System.Windows.Forms.Label?displayProperty=fullName> y <xref:System.Web.UI.WebControls.Label?displayProperty=fullName>).</xref:System.Web.UI.WebControls.Label?displayProperty=fullName> </xref:System.Windows.Forms.Label?displayProperty=fullName> </xref:System.Web.UI.WebControls> </xref:System.Windows.Forms> Si su aplicación utiliza los dos o si define su propio `Label` (clase), debe distinguir los diferentes `Label` objetos. Incluir el alias del espacio de nombres o la importación en la declaración de variable. En el ejemplo siguiente se utiliza el alias de importación.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Miembros de otros elementos que contiene  
 Cuando se utiliza un miembro no compartido de otra clase o estructura, primero debe calificar el nombre de miembro con una variable o expresión que señale a una instancia de la clase o estructura. En el ejemplo siguiente, `demoClass` es una instancia de una clase denominada `class1`.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 No puede utilizar el nombre de la clase para calificar a un miembro que no sea [Shared](../../../../visual-basic/language-reference/modifiers/shared.md). Primero debe crear una instancia en una variable de objeto (en este caso `demoClass`) y, a continuación, hacer referencia a ella por el nombre de variable.  
  
 Si una clase o estructura tiene un `Shared` miembro, puede calificar ese miembro con el nombre de clase o estructura o con una variable o expresión que señale a una instancia.  
  
 Un módulo no tiene ninguna instancia separada y todos sus miembros son `Shared` de forma predeterminada. Por lo tanto, califica a un miembro de módulo con el nombre del módulo.  
  
 El ejemplo siguiente muestra referencias calificadas a procedimientos de miembros de módulo. El ejemplo declara dos `Sub` procedimientos, con el nombre `perform`, en módulos diferentes de un proyecto. Cada uno de ellos puede especificarse sin calificación en su propio módulo, pero debe ser completo si se hace referencia desde cualquier otro lugar. Dado que la última referencia en `module3` no cumple los requisitos `perform`, el compilador no puede resolver esa referencia.  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a>Referencias a proyectos  
 Usar [público](../../../../visual-basic/language-reference/modifiers/public.md) elementos definidos en otro proyecto, primero debe establecer una *referencia* a la biblioteca del proyecto de ensamblado o tipo. Para establecer una referencia, haga clic en **Agregar referencia** en el **proyecto** menú o use la [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) opción del compilador de línea de comandos.  
  
 Por ejemplo, puede utilizar el modelo de objetos XML de la [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Si establece una referencia a la <xref:System.Xml>espacio de nombres, puede declarar y utilizar cualquiera de sus clases, como <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument> </xref:System.Xml> En el ejemplo siguiente se utiliza <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Importar elementos contenedores  
 Puede usar el [Imports (instrucción Namespace .NET y tipo)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) a *importar* los espacios de nombres que contienen los módulos o clases que desea utilizar. Esto permite hacer referencia a los elementos definidos en un espacio de nombres importado sin calificar por completo sus nombres. En el ejemplo siguiente se vuelve a escribir el ejemplo anterior para importar el <xref:System.Xml>espacio de nombres.</xref:System.Xml>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Además, el `Imports` instrucción puede definir un *alias de importación* para cada espacio de nombres importado. Esto puede hacer que el código fuente más corto y fácil de leer. En el ejemplo siguiente se vuelve a escribir el ejemplo anterior para utilizar `xD` como un alias para el <xref:System.Xml>espacio de nombres.</xref:System.Xml>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 El `Imports` no hace que los elementos de otros proyectos disponibles para la aplicación. Es decir, no tiene lugar de la configuración de una referencia. Importar un espacio de nombres sólo quita la necesidad de calificar los nombres definidos en ese espacio de nombres.  
  
 También puede utilizar el `Imports` instrucción para importar módulos, clases, estructuras y enumeraciones. A continuación, puede utilizar a los miembros de estos elementos importados sin calificación. Sin embargo, debe calificar siempre los miembros no compartidos de clases y estructuras con una variable o expresión que se evalúa como una instancia de la clase o estructura.  
  
## <a name="naming-guidelines"></a>Instrucciones de nomenclatura  
 Cuando se definen dos o más elementos de programación que tienen el mismo nombre, un *ambigüedad de nombres* puede producirse cuando el compilador intenta resolver una referencia a ese nombre. Si hay más de una definición en el ámbito, o si ninguna definición está en ámbito, la referencia es irresoluble. Para obtener un ejemplo, vea "Ejemplo de referencia calificada" en esta página de ayuda.  
  
 Para evitar la ambigüedad de nombres proporcionando nombres únicos a todos los elementos. A continuación, puede hacer referencia a cualquier elemento sin tener que calificar su nombre con un espacio de nombres, módulo o clase. También se reduce la posibilidad de hacer referencia accidentalmente a un elemento equivocado.  
  
## <a name="shadowing"></a>Sombrear  
 Si dos elementos de programación comparten el mismo nombre, uno de ellos puede ocultar, o *instantáneas*, otro. Un elemento sombreado no está disponible como referencia; en su lugar, cuando el código utiliza el nombre del elemento sombreado, el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador resuelve en el elemento de sombreado. Para obtener una explicación más detallada con ejemplos, vea [sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="see-also"></a>Vea también  
 [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [NIB Cómo: modificar las propiedades de proyecto y opciones de configuración](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [New (operador)](../../../../visual-basic/language-reference/operators/new-operator.md)   
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)
