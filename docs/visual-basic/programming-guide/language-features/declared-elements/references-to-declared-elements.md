---
title: Referencias a elementos declarados (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 18f9920891e35517efe7adcfd4c03e03ac771478
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655816"
---
# <a name="references-to-declared-elements-visual-basic"></a>Referencias a elementos declarados (Visual Basic)
Cuando el código hace referencia a un elemento declarado, el compilador de Visual Basic coincide con el nombre de la referencia con la declaración pertinente de ese nombre. Si más de un elemento se declara con el mismo nombre, se puede controlar cuál de los elementos se haga referencia a *aplicables* su nombre.  
  
 El compilador intenta hacer coincidir una referencia de nombre con una declaración de nombre con el *ámbito más restringido*. Esto significa se inicia con el código que hace la referencia y hacia afuera funciona a través de niveles sucesivos de elementos contenedores.  
  
 El ejemplo siguiente muestra las referencias a dos variables con el mismo nombre. En el ejemplo se declara dos variables, cada uno denominado `totalCount`, con distintos niveles de ámbito en el módulo `container`. Cuando el procedimiento `showCount` muestra `totalCount` sin calificación, el compilador de Visual Basic resuelve la referencia a la declaración con el ámbito más restringido, concretamente la declaración local dentro de `showCount`. Cuando califica `totalCount` con el módulo contenedor `container`, el compilador resuelve la referencia a la declaración con el ámbito más amplio.  
  
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
 Si desea invalidar este proceso de búsqueda y especificar un nombre declarado en un ámbito más amplio, debe *calificar* el nombre con el elemento contenedor del ámbito más amplio. En algunos casos, también tendrá que calificar el elemento contenedor.  
  
 Calificar un nombre significa que precede en la instrucción de origen con la información que identifica donde se define el elemento de destino. Esta información se denomina un *cadena de calificación*. Puede incluir uno o más espacios de nombres y un módulo, clase o estructura.  
  
 La cadena de calificación debe especificar de forma inequívoca el módulo, clase o estructura que contiene el elemento de destino. El contenedor a su vez podría encontrarse en otro elemento contenedor, normalmente un espacio de nombres. Debe incluir varios elementos contenedores en la cadena de calificación.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Para obtener acceso a un elemento declarado mediante la calificación de su nombre  
  
1.  Determinar la ubicación en la que se ha definido el elemento. Esto podría incluir un espacio de nombres o incluso una jerarquía de espacios de nombres. En el espacio de nombres de nivel inferior, el elemento debe incluirse en un módulo, clase o estructura.  
  
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
  
2.  Determinar una ruta de acceso de calificación basado en la ubicación del elemento de destino. Comience con el espacio de nombres de nivel superior, continúe con el espacio de nombres de nivel inferior y finalizar con el módulo, clase o estructura que contiene el elemento de destino. Cada elemento de la ruta de acceso debe incluir el elemento que lo sigue.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3.  Prepare la cadena de calificación para el elemento de destino. Coloque un punto (`.`) después de cada elemento de la ruta de acceso. La aplicación debe tener acceso a todos los elementos de la cadena de calificación.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  Escribir la expresión o instrucción de asignación que hace referencia al elemento de destino de la forma habitual.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  Delante del nombre de elemento de destino con la cadena de calificación. El nombre debe seguir inmediatamente el período (`.`) que sigue el módulo, clase o estructura que contiene el elemento.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  El compilador utiliza la cadena de calificación para encontrar una declaración clara y no ambigua, que puede coincidir con la referencia de elemento de destino.  
  
 También podría tener que calificar una referencia de nombre si la aplicación tiene acceso a más de un elemento de programación que tiene el mismo nombre. Por ejemplo, el <xref:System.Windows.Forms> y <xref:System.Web.UI.WebControls> espacios de nombres ambos contienen una `Label` clase (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> y <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>). Si la aplicación utiliza ambos, o si define su propio `Label` (clase), debe distinguir los diferentes `Label` objetos. Incluir el alias de espacio de nombres o importar en la declaración de variable. En el ejemplo siguiente se utiliza el alias de importación.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Miembros de otros elementos que contiene  
 Cuando se utiliza un miembro no compartido de otra clase o estructura, primero debe calificar el nombre del miembro con una variable o expresión que apunta a una instancia de la clase o estructura. En el ejemplo siguiente, `demoClass` es una instancia de una clase denominada `class1`.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 No se puede usar el nombre de la clase para calificar a un miembro que no sea [Shared](../../../../visual-basic/language-reference/modifiers/shared.md). Primero debe crear una instancia en una variable de objeto (en este caso `demoClass`) y, a continuación, hacer referencia a él mediante el nombre de variable.  
  
 Si una clase o estructura tiene un `Shared` miembro, puede calificar ese miembro con el nombre de clase o estructura o con una variable o expresión que apunta a una instancia.  
  
 Un módulo no tiene ninguna instancia separada y todos sus miembros son `Shared` de forma predeterminada. Por lo tanto, califica a un miembro de módulo con el nombre del módulo.  
  
 En el ejemplo siguiente se muestra referencias completas a los procedimientos de miembros de módulo. El ejemplo declara dos `Sub` procedimientos, ambos denominados `perform`, en módulos diferentes de un proyecto. Cada uno de ellos puede especificarse sin calificación en su propio módulo, pero debe ser completo si se hace referencia desde cualquier otro lugar. Dado que la última referencia en `module3` no cumple los requisitos `perform`, el compilador no puede resolver esa referencia.  
  
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
 Usar [público](../../../../visual-basic/language-reference/modifiers/public.md) elementos definidos en otro proyecto, primero debe establecer un *referencia* del ese proyecto ensamblado o biblioteca de tipos. Para establecer una referencia, haga clic en **Agregar referencia** en el **proyecto** menú o use la [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) opción del compilador de línea de comandos.  
  
 Por ejemplo, puede usar el modelo de objetos XML de la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Si establece una referencia a la <xref:System.Xml> espacio de nombres, puede declarar y utilizar cualquiera de sus clases, como <xref:System.Xml.XmlDocument>. En el ejemplo siguiente se utiliza <xref:System.Xml.XmlDocument>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Importar elementos contenedores  
 Puede usar el [Imports (instrucción Namespace de .NET y tipo)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) a *importar* los espacios de nombres que contienen los módulos o clases que desea utilizar. Esto permite hacer referencia a los elementos definidos en un espacio de nombres importado sin calificar por completo sus nombres. En el ejemplo siguiente se vuelve a escribir el ejemplo anterior para importar el <xref:System.Xml> espacio de nombres.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Además, el `Imports` instrucción puede definir un *alias de importación* para cada espacio de nombres importado. Esto puede hacer que el código fuente más corto y fácil de leer. En el ejemplo siguiente se vuelve a escribir el ejemplo anterior para usar `xD` como un alias para el <xref:System.Xml> espacio de nombres.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 El `Imports` instrucción no hace que estén disponibles para la aplicación de elementos de otros proyectos. Es decir, no tienen el lugar de establecer una referencia. Importar un espacio de nombres solo elimina el requisito para calificar los nombres definidos en ese espacio de nombres.  
  
 También puede usar el `Imports` statement para importar módulos, clases, estructuras y enumeraciones. A continuación, puede utilizar a los miembros de estos elementos importados sin calificación. Sin embargo, debe calificar siempre los miembros no compartidos de clases y estructuras con una variable o expresión que se evalúa como una instancia de la clase o estructura.  
  
## <a name="naming-guidelines"></a>Instrucciones de nomenclatura  
 Cuando se definen dos o más elementos de programación que tienen el mismo nombre, un *ambigüedad de nombres* se pueden producir cuando el compilador intenta resolver una referencia a ese nombre. Si hay más de una definición en el ámbito, o si ninguna definición está en el ámbito, la referencia es irresoluble. Para obtener un ejemplo, vea "Ejemplo de referencia calificada" en esta página de ayuda.  
  
 Puede evitar la ambigüedad de nombre dando a todos los elementos nombres únicos. A continuación, puede hacer referencia a cualquier elemento sin tener que calificar su nombre con un espacio de nombres, módulo o clase. También se reduce la posibilidad de hacer referencia accidentalmente al elemento incorrecto.  
  
## <a name="shadowing"></a>Sombrear  
 Si dos elementos de programación comparten el mismo nombre, uno de ellos puede ocultar, o *instantáneas*, el otro se. Un elemento reemplazado no está disponible como referencia; en su lugar, cuando el código usa el nombre del elemento sombreado, el compilador de Visual Basic resuelve en el elemento reemplazado. Para obtener una explicación más detallada con ejemplos, vea [sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="see-also"></a>Vea también  
 [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)  
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Imports (instrucción), espacio de nombres y tipo .NET](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [New (operador)](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)
