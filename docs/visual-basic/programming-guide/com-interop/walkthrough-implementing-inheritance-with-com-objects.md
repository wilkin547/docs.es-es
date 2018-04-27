---
title: 'Tutorial: Implementar la herencia mediante objetos COM (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 10c6bdf46e351b23705107da3b693531718cfd37
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Tutorial: Implementar la herencia mediante objetos COM (Visual Basic)
Puede derivar clases de Visual Basic de `Public` clases de objetos COM, incluso los creados en versiones anteriores de Visual Basic. Las propiedades y métodos de las clases heredadas de objetos COM pueden reemplazar o sobrecargar al igual que las propiedades y métodos de cualquier otra clase base se pueden reemplazar o sobrecargar. Herencia de objetos COM resulta útil cuando tiene una biblioteca de clases existentes que no desea volver a compilar.  
  
 El siguiente procedimiento muestra cómo usar Visual Basic 6.0 para crear un objeto COM que contiene una clase y, a continuación, utilizarlo como una clase base.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>Para generar el objeto COM que se utiliza en este tutorial  
  
1.  En Visual Basic 6.0, abra un nuevo proyecto de DLL de ActiveX. Un proyecto denominado `Project1` se crea. Tiene una clase denominada `Class1`.  
  
2.  En el **el Explorador de proyectos**, haga clic en **Proyecto1**y, a continuación, haga clic en **propiedades de Project1**. El **propiedades del proyecto** se muestra el cuadro de diálogo.  
  
3.  En el **General** pestaña de la **propiedades del proyecto** cuadro de diálogo, cambie el nombre del proyecto escribiendo `ComObject1` en el **nombre del proyecto** campo.  
  
4.  En el **el Explorador de proyectos**, haga clic en `Class1`y, a continuación, haga clic en **propiedades**. El **propiedades** se muestra la ventana de la clase.  
  
5.  Cambiar el `Name` propiedad `MathFunctions`.  
  
6.  En el **el Explorador de proyectos**, haga clic en `MathFunctions`y, a continuación, haga clic en **ver código**. El **Editor de código** se muestra.  
  
7.  Agregue una variable local para almacenar el valor de propiedad:  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  Agregar propiedad `Let` y propiedad `Get` property (procedimientos):  
  
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
  
10. Cree y registre el objeto COM, haga clic en **realizar ComObject1.dll** en el **archivo** menú.  
  
    > [!NOTE]
    >  Aunque también puede exponer una clase creada con Visual Basic como un objeto COM, no es un objeto COM es true y no se puede usar en este tutorial. Para obtener más información, consulte [interoperabilidad COM en aplicaciones de .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="interop-assemblies"></a>Ensamblados de interoperabilidad  
 En el siguiente procedimiento, creará un ensamblado de interoperabilidad, que actúa como un puente entre el código administrado y el código no administrado (por ejemplo, un objeto COM) [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] utiliza. El ensamblado de interoperabilidad que crea Visual Basic controla muchos de los detalles sobre cómo trabajar con objetos COM, como *la serialización de interoperabilidad*, el proceso de empaquetado de parámetros y valores devueltos en datos equivalentes tipos tal y como se mueven a y de los objetos COM. La referencia de la aplicación Visual Basic apunta al ensamblado de interoperabilidad, no al objeto COM real.  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Para utilizar un objeto COM con Visual Basic 2005 y versiones posteriores  
  
1.  Abra un nuevo proyecto de aplicación de Windows de Visual Basic.  
  
2.  En el menú **Proyecto**, haga clic en **Agregar referencia**.  
  
     Aparecerá el cuadro de diálogo **Agregar referencia**.  
  
3.  En el **COM** ficha, haga doble clic en `ComObject1` en el **nombre de componente** lista y haga clic en **Aceptar**.  
  
4.  En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.  
  
     Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.  
  
5.  En el **plantillas** panel, haga clic en **clase**.  
  
     El nombre de archivo predeterminado, `Class1.vb`, aparece en la **nombre** campo. Modifique este campo a MathClass.vb y haga clic en **agregar**. Esto crea una clase denominada `MathClass`y muestra su código.  
  
6.  Agregue el código siguiente al principio del `MathClass` heredar de la clase COM.  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  Sobrecargar el método público de la clase base agregando el código siguiente a `MathClass`:  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  Extender la clase heredada agregando el código siguiente a `MathClass`:  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 La nueva clase hereda las propiedades de la clase base en el objeto COM, sobrecarga un método y define un nuevo método para extender la clase.  
  
#### <a name="to-test-the-inherited-class"></a>Para probar la clase heredada  
  
1.  Agregar un botón al formulario de inicio y, a continuación, haga doble clic en él para ver su código.  
  
2.  En el botón `Click` procedimiento del controlador de eventos, agregue el código siguiente para crear una instancia de `MathClass` y llamar a los métodos sobrecargados:  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  Ejecute el proyecto presionando F5.  
  
 Al hacer clic en el botón en el formulario, el `AddNumbers` método se llama por primera vez con `Short` números, tipo de datos y Visual Basic, se elegirá el método apropiado de la clase base. La segunda llamada a `AddNumbers` se dirige a la sobrecarga del método de `MathClass`. La tercera llamar llamadas el `SubtractNumbers` método, que extiende la clase. Se establece la propiedad en la clase base, y se muestra el valor.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Es podrán que haya observado que sobrecargado `AddNumbers` función parece tener los mismos datos de tipo que el método se hereda de la clase base del objeto COM. Esto es porque los argumentos y parámetros de método de clase base están definidos como enteros de 16 bits en Visual Basic 6.0, pero se exponen como enteros de 16 bits de tipo `Short` en versiones posteriores de Visual Basic. La nueva función acepta enteros de 32 bits y sobrecarga la función de clase base.  
  
 Cuando se trabaja con objetos COM, asegúrese de comprobar el tamaño y tipos de datos de parámetros. Por ejemplo, cuando se utiliza un objeto COM que acepta un objeto de colección de Visual Basic 6.0 como argumento, no puede proporcionar una colección de una versión posterior de Visual Basic.  
  
 Se reemplazan propiedades y métodos heredados de clases COM, lo que significa que se puede declarar una propiedad local o un método que reemplaza una propiedad o método heredado de una clase COM base. Las reglas para reemplazar propiedades COM heredadas son similares a las reglas para reemplazar otras propiedades y métodos con las siguientes excepciones:  
  
-   Si reemplaza cualquier propiedad o método heredado de una clase COM, debe reemplazar todas las demás propiedades heredadas y métodos.  
  
-   Propiedades que usan `ByRef` parámetros no se puede invalidar.  
  
## <a name="see-also"></a>Vea también  
 [Interoperabilidad COM en aplicaciones .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Short (tipo de datos)](../../../visual-basic/language-reference/data-types/short-data-type.md)
