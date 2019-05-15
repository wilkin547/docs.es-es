---
title: Referencias a elementos declarados (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 616599e15c0d3d4c2177622d6820269bcff3ea39
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592802"
---
# <a name="references-to-declared-elements-visual-basic"></a>Referencias a elementos declarados (Visual Basic)
Cuando el código hace referencia a un elemento declarado, el compilador de Visual Basic coincide con el nombre de la referencia a la declaración adecuada de ese nombre. Si se declara más de un elemento con el mismo nombre, puede controlar cuál de estos elementos es hacer referencia a *calificación* su nombre.  
  
 El compilador intenta hacer coincidir una referencia de nombre a una declaración de nombre con el *ámbito más restringido*. Esto significa se inicia con el código que hace la referencia y se lleva a través de los niveles sucesivos de los elementos contenedores.  
  
 El ejemplo siguiente muestra las referencias a dos variables con el mismo nombre. En el ejemplo se declara dos variables, cada uno denominado `totalCount`, en diferentes niveles de ámbito en el módulo `container`. Cuando el procedimiento `showCount` muestra `totalCount` sin calificación, el compilador de Visual Basic resuelve la referencia a la declaración con el ámbito más restringido, concretamente la declaración local dentro de `showCount`. Cuando califica `totalCount` con el módulo contenedor `container`, el compilador resuelve la referencia a la declaración con el ámbito más amplio.  
  
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
  
 Calificar un nombre significa que le precede en la instrucción de origen con la información que identifica donde se define el elemento de destino. Esta información se conoce como un *cadena de calificación*. Puede incluir uno o más espacios de nombres y un módulo, clase o estructura.  
  
 La cadena de calificación debe especificar de forma inequívoca el módulo, clase o estructura que contiene el elemento de destino. El contenedor a su vez puede estar ubicado en otro elemento contenedor, normalmente un espacio de nombres. Es posible que deba incluir varios elementos contenedores en la cadena de calificación.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Para obtener acceso a un elemento declarado por su nombre  
  
1. Determinar la ubicación en la que se ha definido el elemento. Esto podría incluir un espacio de nombres o incluso una jerarquía de espacios de nombres. En el espacio de nombres de nivel más bajo, el elemento debe incluirse en un módulo, clase o estructura.  
  
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
  
2. Determinar una ruta de acceso de calificación según la ubicación del elemento de destino. Comience con el espacio de nombres de nivel superior, continúe con el espacio de nombres de nivel inferior y terminar con el módulo, clase o estructura que contiene el elemento de destino. Cada elemento de la ruta de acceso debe incluir el elemento que le sigue.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3. Prepare la cadena de calificación para el elemento de destino. Escriba un punto (`.`) después de todos los elementos de la ruta de acceso. La aplicación debe tener acceso a todos los elementos de la cadena de calificación.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. Escribir la expresión o instrucción de asignación que hace referencia al elemento de destino de la manera normal.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. Delante del nombre de elemento de destino con la cadena de calificación. El nombre debe seguir inmediatamente el período (`.`) que sigue el módulo, clase o estructura que contiene el elemento.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. El compilador usa la cadena de calificación para encontrar una declaración, inequívoca a la que puede coincidir con la referencia de elemento de destino.  
  
 También es posible que deba calificar una referencia de nombre si la aplicación tiene acceso a más de un elemento de programación que tiene el mismo nombre. Por ejemplo, el <xref:System.Windows.Forms> y <xref:System.Web.UI.WebControls> espacios de nombres ambos contienen una `Label` clase (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> y <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>). Si la aplicación utiliza los dos, o bien, si define su propio `Label` (clase), se deben distinguir los diferentes `Label` objetos. Incluir el alias de espacio de nombres o importar en la declaración de variable. El ejemplo siguiente usa el alias de importación.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Miembros de otros elementos que contiene  
 Cuando se usa un miembro no compartido de otra clase o estructura, primero debe calificar el nombre del miembro con una variable o expresión que apunta a una instancia de la clase o estructura. En el ejemplo siguiente, `demoClass` es una instancia de una clase denominada `class1`.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 No se puede usar el nombre de la clase para calificar a un miembro que no es [Shared](../../../../visual-basic/language-reference/modifiers/shared.md). Primero debe crear una instancia en una variable de objeto (en este caso `demoClass`) y, a continuación, haga referencia a él por el nombre de variable.  
  
 Si una clase o estructura tiene un `Shared` miembros, puede calificar ese miembro con el nombre de clase o estructura o con una variable o expresión que apunta a una instancia.  
  
 Un módulo no tiene todas las instancias independientes, y todos sus miembros son `Shared` de forma predeterminada. Por lo tanto, para calificar al miembro de un módulo con el nombre del módulo.  
  
 El ejemplo siguiente muestra referencias completas a los procedimientos de miembros de módulo. El ejemplo declara dos `Sub` procedimientos, ambos denominados `perform`, en módulos diferentes de un proyecto. Cada una de ellas puede especificarse sin calificación en su propio módulo, pero debe ser completa si se hace referencia desde cualquier otro lugar. Dado que hacen referencia a la última en `module3` no cumple los requisitos `perform`, el compilador no puede resolver esa referencia.  
  
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
 Para usar [pública](../../../../visual-basic/language-reference/modifiers/public.md) elementos definidos en otro proyecto, primero debe establecer un *referencia* del ese proyecto ensamblado o biblioteca de tipos. Para establecer una referencia, haga clic en **Agregar referencia** en el **proyecto** menú o use el [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) opción del compilador de línea de comandos.  
  
 Por ejemplo, puede usar el modelo de objetos XML de .NET Framework. Si establece una referencia a la <xref:System.Xml> espacio de nombres, puede declarar y usar cualquiera de sus clases, como <xref:System.Xml.XmlDocument>. En el ejemplo siguiente se usa <xref:System.Xml.XmlDocument>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Importar elementos contenedores  
 Puede usar el [instrucción Imports (tipo y Namespace. NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) a *importar* los espacios de nombres que contienen los módulos o clases que se va a usar. Esto le permite hacer referencia a los elementos definidos en un espacio de nombres importado sin calificar por completo sus nombres. El ejemplo siguiente se vuelve a escribir el ejemplo anterior para importar el <xref:System.Xml> espacio de nombres.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Además, el `Imports` instrucción puede definir un *alias de importación* para cada espacio de nombres importado. Esto puede hacer que el código fuente más corto y fácil de leer. El ejemplo siguiente se vuelve a escribir el ejemplo anterior se usan `xD` como un alias para el <xref:System.Xml> espacio de nombres.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 El `Imports` no hace que los elementos de otros proyectos disponibles para la aplicación. Es decir, no tiene lugar de la configuración de una referencia. Importar un espacio de nombres solo quita el requisito para calificar los nombres definidos en dicho espacio de nombres.  
  
 También puede usar el `Imports` instrucción para importar módulos, clases, estructuras y enumeraciones. A continuación, puede utilizar a los miembros de estos elementos importados sin calificación. Sin embargo, siempre debe calificar a los miembros no compartidos de clases y estructuras con una variable o expresión que se evalúa como una instancia de la clase o estructura.  
  
## <a name="naming-guidelines"></a>Instrucciones de nomenclatura  
 Cuando se definen dos o más elementos de programación que tienen el mismo nombre, un *nombre ambigüedad* puede producir cuando el compilador intenta resolver una referencia a ese nombre. Si hay más de una definición en el ámbito, o si ninguna definición está en el ámbito, la referencia es irresoluble. Para obtener un ejemplo, vea "Ejemplo de referencia completo" en esta página de ayuda.  
  
 Puede evitar la ambigüedad de nombre proporcionando nombres únicos a todos los elementos. A continuación, puede hacer referencia a cualquier elemento sin tener que calificar su nombre con un espacio de nombres, módulo o clase. También reduce las posibilidades de accidentalmente que hace referencia a un elemento equivocado.  
  
## <a name="shadowing"></a>Sombreado  
 Cuando dos elementos de programación comparten el mismo nombre, puede ocultar uno de ellos, o *sombra*, otro. Un elemento reemplazado no está disponible para la referencia; en su lugar, cuando el código usa el nombre del elemento reemplazado, el compilador de Visual Basic resuelve en el elemento reemplazado. Para obtener una explicación más detallada con ejemplos, vea [sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="see-also"></a>Vea también

- [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
- [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Imports (instrucción), espacio de nombres y tipo .NET](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [New (operador)](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Public](../../../../visual-basic/language-reference/modifiers/public.md)
