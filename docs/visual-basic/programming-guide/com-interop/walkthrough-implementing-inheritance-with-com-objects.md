---
title: 'Tutorial: Implementar la herencia mediante objetos COM (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: a1c1b7c247d3277c6614a4774395650c4c069c2f
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930003"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Tutorial: Implementar la herencia mediante objetos COM (Visual Basic)
Puede derivar clases de Visual Basic desde `Public` clases de objetos COM, incluso los creados en versiones anteriores de Visual Basic. Las propiedades y métodos de clases que heredan de los objetos COM pueden ser invalidados o sobrecargados solo como propiedades y métodos de cualquier otra clase base pueden ser invalidados o sobrecargados. Herencia de objetos COM resulta útil cuando tiene una biblioteca de clases que no desea volver a compilar.  
  
 El procedimiento siguiente muestra cómo usar Visual Basic 6.0 para crear un objeto COM que contiene una clase y, a continuación, usarlo como clase base.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>Para crear el objeto COM que se usa en este tutorial  
  
1.  En Visual Basic 6.0, abra un nuevo proyecto de DLL de ActiveX. Un proyecto denominado `Project1` se crea. Tiene una clase denominada `Class1`.  
  
2.  En el **Explorador de proyectos**, haga clic en **Project1**y, a continuación, haga clic en **Project1 propiedades**. El **las propiedades del proyecto** se muestra el cuadro de diálogo.  
  
3.  En el **General** pestaña de la **las propiedades del proyecto** cuadro de diálogo, cambie el nombre del proyecto escribiendo `ComObject1` en el **nombre del proyecto** campo.  
  
4.  En el **Explorador de proyectos**, haga clic en `Class1`y, a continuación, haga clic en **propiedades**. El **propiedades** se muestra la ventana de la clase.  
  
5.  Cambiar el `Name` propiedad `MathFunctions`.  
  
6.  En el **Explorador de proyectos**, haga clic en `MathFunctions`y, a continuación, haga clic en **ver código**. El **Editor de código** se muestra.  
  
7.  Agregue una variable local para almacenar el valor de propiedad:  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  Agregar propiedad `Let` y propiedad `Get` procedimientos de propiedad:  
  
    ```  
    Public Property Let Prop1(ByVal vData As Integer)  
       'Used when assigning a value to the property.  
       mvarProp1 = vData  
    End Property  
    Public Property Get Prop1() As Integer  
       'Used when retrieving a property's value.  
       Prop1 = mvarProp1  
    End Property  
    ```  
  
9. Agregue una función:  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. Crear y registrar el objeto COM haciendo **ComObject1.dll realizar** en el **archivo** menú.  
  
    > [!NOTE]
    >  También puede exponer una clase creada con Visual Basic como un objeto COM, no es un verdadero objeto COM y no se puede usar en este tutorial. Para obtener más información, consulte [interoperabilidad COM en aplicaciones de .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="interop-assemblies"></a>Ensamblados de interoperabilidad  
 En el siguiente procedimiento, creará un ensamblado de interoperabilidad, que actúa como puente entre el código no administrado (por ejemplo, un objeto COM) y el código administrado que usa Visual Studio. El ensamblado de interoperabilidad que crea Visual Basic controla muchos de los detalles del trabajo con objetos COM, como *la serialización de interoperabilidad*, el proceso de empaquetado de parámetros y valores devueltos en datos equivalentes tipos cuando se mueven a y de objetos COM. La referencia de la aplicación Visual Basic apunta al ensamblado de interoperabilidad, no al objeto COM real.  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Para utilizar un objeto COM con Visual Basic 2005 y versiones posteriores  
  
1.  Abra un proyecto Aplicación Windows de Visual Basic nuevo.  
  
2.  En el menú **Proyecto**, haga clic en **Agregar referencia**.  
  
     Aparecerá el cuadro de diálogo **Agregar referencia**.  
  
3.  En el **COM** , haga doble clic `ComObject1` en el **nombre del componente** lista y haga clic en **Aceptar**.  
  
4.  En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.  
  
     Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.  
  
5.  En el **plantillas** panel, haga clic en **clase**.  
  
     El nombre de archivo predeterminado, `Class1.vb`, aparece en el **nombre** campo. Modifique este campo MathClass.vb y haga clic en **agregar**. Esto crea una clase denominada `MathClass`y muestra su código.  
  
6.  Agregue el código siguiente al principio del `MathClass` para heredar de la clase COM.  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  Sobrecargar el método público de la clase base agregando el código siguiente al `MathClass`:  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  Extender la clase heredada agregando el código siguiente al `MathClass`:  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 La nueva clase hereda las propiedades de la clase base en el objeto COM, sobrecarga un método y define un nuevo método para extender la clase.  
  
#### <a name="to-test-the-inherited-class"></a>Para probar la clase heredada  
  
1.  Agregue un botón al formulario de inicio y, a continuación, haga doble clic en él para ver su código.  
  
2.  En el botón `Click` procedimiento del controlador de eventos, agregue el código siguiente para crear una instancia de `MathClass` y llamar a los métodos sobrecargados:  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  Ejecute el proyecto presionando F5.  
  
 Al hacer clic en el botón en el formulario, el `AddNumbers` primero se llama al método con `Short` números, tipo de datos y Visual Basic, se elige el método adecuado de la clase base. La segunda llamada a `AddNumbers` se dirige a la sobrecarga del método de `MathClass`. La tercera llamadas llamadas la `SubtractNumbers` método, que extiende la clase. Se establece la propiedad de la clase base, y se muestra el valor.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Es podrán que haya observado que sobrecargado `AddNumbers` función parece tener los mismos datos de tipo que el método se hereda de la clase base del objeto COM. Esto es porque los argumentos y parámetros de método de clase base se definen como enteros de 16 bits en Visual Basic 6.0, pero se exponen como enteros de 16 bits de tipo `Short` en versiones posteriores de Visual Basic. La nueva función acepta enteros de 32 bits y sobrecarga de la función de la clase base.  
  
 Cuando se trabaja con objetos COM, asegúrese de que compruebe el tamaño y tipos de datos de parámetros. Por ejemplo, cuando se usa un objeto COM que acepta un objeto de colección de Visual Basic 6.0 como argumento, no puede proporcionar una colección de una versión posterior de Visual Basic.  
  
 Pueden invalidar las propiedades y métodos heredados de las clases COM, lo que significa que puede declarar una propiedad local o un método que reemplaza una propiedad o método heredado de una clase COM base. Las reglas para reemplazar propiedades COM heredadas son similares a las reglas para reemplazar otras propiedades y métodos con las siguientes excepciones:  
  
-   Si reemplaza cualquier propiedad o método heredado de una clase COM, debe reemplazar todas las demás propiedades heredadas y métodos.  
  
-   Las propiedades que usan `ByRef` no se puede invalidar los parámetros.  
  
## <a name="see-also"></a>Vea también  
 [Interoperabilidad COM en aplicaciones .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Short (tipo de datos)](../../../visual-basic/language-reference/data-types/short-data-type.md)
