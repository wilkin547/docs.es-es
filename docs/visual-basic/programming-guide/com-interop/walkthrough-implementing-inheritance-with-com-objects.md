---
title: 'Tutorial: Implementar la herencia mediante objetos COM (Visual Basic) | Documentos de Microsoft'
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
- inheritance, COM reusability
- base classes, COM reusability
- inheritance, walkthroughs
- derived classes, COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
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
ms.openlocfilehash: fa7753847619f14600c924cba01e55651c4f17c2
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Tutorial: Implementar la herencia mediante objetos COM (Visual Basic)
Puede derivar clases de Visual Basic desde `Public` clases de objetos COM, incluso los creados en versiones anteriores de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Las propiedades y métodos de las clases heredadas de objetos COM pueden reemplazar o sobrecargar sólo como propiedades y métodos de cualquier otra clase base se pueden reemplazar o sobrecargar. Herencia de objetos COM resulta útil cuando tiene una biblioteca de clases que no desea volver a compilar.  
  
 El siguiente procedimiento muestra cómo utilizar Visual Basic 6.0 para crear un objeto COM que contiene una clase y utilizarlo como una clase base.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>Para generar el objeto COM que se utiliza en este tutorial  
  
1.  En Visual Basic 6.0, abra un nuevo proyecto de DLL de ActiveX. Un proyecto denominado `Project1` se crea. Tiene una clase denominada `Class1`.  
  
2.  En el **el Explorador de proyectos**, haga clic en **Project1**y, a continuación, haga clic en **propiedades de Project1**. El **propiedades del proyecto** se muestra el cuadro de diálogo.  
  
3.  En el **General** ficha de la **propiedades del proyecto** cuadro de diálogo, cambie el nombre del proyecto escribiendo `ComObject1` en el **nombre de proyecto** campo.  
  
4.  En el **el Explorador de proyectos**, haga clic en `Class1`y, a continuación, haga clic en **propiedades**. El **propiedades** se muestra la ventana de la clase.  
  
5.  Cambiar el `Name` propiedad `MathFunctions`.  
  
6.  En el **el Explorador de proyectos**, haga clic en `MathFunctions`y, a continuación, haga clic en **ver código**. El **Editor de código** se muestra.  
  
7.  Agregue una variable local para contener el valor de propiedad:  
  
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
  
10. Cree y registre el objeto COM, haga clic en **hacer ComObject1.dll** en el **archivo** menú.  
  
    > [!NOTE]
    >  También puede exponer una clase creada con [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] como un objeto COM, que no es un verdadero objeto COM y no se puede utilizar en este tutorial. Para obtener más información, consulte [interoperabilidad COM en aplicaciones de .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="interop-assemblies"></a>Ensamblados de interoperabilidad  
 En el siguiente procedimiento, creará un ensamblado de interoperabilidad, que actúa como un puente entre el código administrado y el código no administrado (como un objeto COM) [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] utiliza. El ensamblado de interoperabilidad que [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] crea controla muchos de los detalles de cómo trabajar con COM objetos, como *interoperativo*, el proceso de empaquetado de parámetros y valores devueltos en datos equivalentes tipos cuando se mueven hacia y desde objetos COM. La referencia en el [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] puntos de aplicación al ensamblado de interoperabilidad, no al objeto COM real.  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Para utilizar un objeto COM con Visual Basic 2005 y versiones posteriores  
  
1.  Abra un nuevo [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] el proyecto de aplicación de Windows.  
  
2.  En el **proyecto** menú, haga clic en **Agregar referencia**.  
  
     El **Agregar referencia** se muestra el cuadro de diálogo.  
  
3.  En el **COM** , haga doble clic `ComObject1` en el **nombre de componente** y haga clic en **Aceptar**.  
  
4.  En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.  
  
     El **Agregar nuevo elemento** se muestra el cuadro de diálogo.  
  
5.  En el **plantillas** panel, haga clic en **clase**.  
  
     El nombre de archivo predeterminado, `Class1.vb`, aparece en la **nombre** campo. Modifique este campo a MathClass.vb y haga clic en **agregar**. Esto crea una clase denominada `MathClass`y muestra su código.  
  
6.  Agregue el código siguiente al principio de `MathClass` para heredar de la clase COM.  
  
     [!code-vb[VbVbalrInterop&#31;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  Sobrecargue el método público de la clase base agregando el código siguiente a `MathClass`:  
  
     [!code-vb[VbVbalrInterop&#32;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  Amplíe la clase heredada agregando el código siguiente a `MathClass`:  
  
     [!code-vb[VbVbalrInterop Nº&33;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 La nueva clase hereda las propiedades de la clase base del objeto COM, sobrecarga un método y define un método para extender la clase.  
  
#### <a name="to-test-the-inherited-class"></a>Para probar la clase heredada  
  
1.  Agregue un botón al formulario de inicio y, a continuación, haga doble clic en él para ver su código.  
  
2.  En el botón `Click` procedimiento del controlador de eventos, agregue el código siguiente para crear una instancia de `MathClass` y llamar a los métodos sobrecargados:  
  
     [!code-vb[VbVbalrInterop&#34;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  Ejecute el proyecto presionando F5.  
  
 Al hacer clic en el botón en el formulario, el `AddNumbers` método se llama por primera vez con `Short` números, tipo de datos y [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] elegirá el método apropiado de la clase base. La segunda llamada a `AddNumbers` se dirige a la sobrecarga del método de `MathClass`. La tercera llamada llama la `SubtractNumbers` método, que extiende la clase. Se establece la propiedad en la clase base y se muestra el valor.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Es podrán que haya observado que sobrecargado `AddNumbers` función parece tener los mismos datos de tipo que el método heredado de la clase base del objeto COM. Esto es porque los argumentos y parámetros de método de clase base están definidos como enteros de 16 bits en Visual Basic 6.0, pero se exponen como enteros de 16 bits de tipo `Short` en versiones posteriores de Visual Basic. La nueva función acepta enteros de 32 bits y sobrecarga la función de clase base.  
  
 Al trabajar con objetos COM, asegúrese de comprobar el tamaño y tipos de datos de parámetros. Por ejemplo, cuando se utiliza un objeto COM que acepta un objeto de colección de Visual Basic 6.0 como argumento, no puede proporcionar una colección de una versión posterior de Visual Basic.  
  
 Se reemplazan propiedades y métodos heredados de clases COM, lo que significa que se puede declarar una propiedad local o un método que reemplaza una propiedad o método heredado de una clase COM base. Las reglas para reemplazar propiedades COM heredadas son similares a las reglas para reemplazar otras propiedades y métodos con las siguientes excepciones:  
  
-   Si reemplaza cualquier propiedad o método heredado de una clase COM, debe reemplazar todas las demás propiedades heredadas y métodos.  
  
-   Propiedades que utilizan `ByRef` no se puede invalidar los parámetros.  
  
## <a name="see-also"></a>Vea también  
 [Interoperabilidad COM en aplicaciones de .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Short (tipo de datos)](../../../visual-basic/language-reference/data-types/short-data-type.md)
