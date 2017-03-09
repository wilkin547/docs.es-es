---
title: "Tutorial: Implementar la herencia mediante objetos COM (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "clases base, reutilización COM"
  - "clases derivadas, reutilización COM"
  - "herencia, reutilización COM"
  - "herencia, tutoriales"
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Tutorial: Implementar la herencia mediante objetos COM (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Se pueden derivar clases de Visual Basic de las clases `Public` de objetos COM, incluso si se crearon en versiones anteriores de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Las propiedades y métodos de las clases heredadas de objetos COM pueden ser invalidados o sobrecargados del mismo modo que las propiedades y métodos de cualquier otra clase base.  La herencia de objetos COM resulta útil cuando se tiene una biblioteca de clases que no se desea volver a compilar.  
  
 En el procedimiento siguiente se muestra cómo usar Visual Basic 6.0 para crear un objeto COM que contiene una clase y, a continuación, utilizar éste como clase base.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Para compilar el objeto COM que se utiliza en este tutorial  
  
1.  En Visual Basic 6.0, abra un proyecto de archivo DLL ActiveX nuevo.  Se crea un proyecto denominado `Project1`.  Tiene una clase denominada `Class1`.  
  
2.  En el **Explorador de proyectos**, haga clic con el botón secundario del mouse en **Project1** y, a continuación, haga clic en **Propiedades de Project1**.  Aparece el cuadro de diálogo **Propiedades del proyecto**.  
  
3.  En la ficha **General** del cuadro de diálogo **Propiedades del proyecto**, escriba `ComObject1` en el campo **Nombre de proyecto** para cambiar el nombre del proyecto.  
  
4.  En el **Explorador de proyectos**, haga clic con el botón secundario del mouse en `Class1` y, a continuación, haga clic en **Propiedades**.  Aparecerá la ventana **Propiedades** correspondiente a la clase.  
  
5.  Establezca la propiedad `Name` en `MathFunctions`.  
  
6.  En el **Explorador de proyectos**, haga clic con el botón secundario del mouse en `MathFunctions` y, a continuación, haga clic en **Ver código**.  Aparece el **Editor de código**.  
  
7.  Agregue una variable local, que contendrá el valor de propiedad:  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  Agregue los procedimientos de propiedad `Let` y `Get`:  
  
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
  
10. Cree y registre el objeto COM; para ello, haga clic en **Crear ComObject1.dll** en el menú **Archivo**.  
  
    > [!NOTE]
    >  Aunque es posible exponer una clase creada con [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] como un objeto COM, en realidad, no se trata de un verdadero objeto COM y no se puede utilizar en este tutorial.  Para obtener información detallada, vea [Interoperabilidad COM en aplicaciones .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## Ensamblados de interoperabilidad  
 En el procedimiento siguiente va a crear un ensamblado de interoperabilidad que servirá como puente entre el código no administrado \(como un objeto COM\) y el código administrado que utiliza [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)].  El ensamblado de interoperabilidad creado por [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] controla muchos de los aspectos del trabajo con objetos COM, como el *cálculo de referencias de interoperabilidad*, el proceso de empaquetado de parámetros y valores devueltos en los tipos de datos equivalentes enviados a objetos COM \(o recibidos de objetos COM\).  La referencia de la aplicación de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] apunta al ensamblado de interoperabilidad, no al objeto COM real.  
  
#### Para utilizar un objeto COM con Visual Basic 2005 y versiones posteriores  
  
1.  Abra un nuevo proyecto de aplicación para Windows de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
2.  Haga clic en la opción **Agregar referencia** del menú **Proyecto**.  
  
     Aparecerá el cuadro de diálogo **Agregar referencia**.  
  
3.  En la ficha **COM**, haga doble clic en `ComObject1` en la lista **Nombre de componente** y, a continuación, haga clic en **Aceptar**.  
  
4.  En el menú **Proyecto**, haga clic en **Agregar nuevo elemento**.  
  
     Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.  
  
5.  En el panel **Plantillas**, haga clic en **Clase**.  
  
     En el campo **Nombre** aparecerá el nombre de archivo predeterminado, `Class1.vb`.  Cambie este campo a MathClass.vb y haga clic en **Agregar**.  Esto creará una clase denominada `MathClass` y mostrará su código.  
  
6.  Agregue el código siguiente al principio de `MathClass` para heredar de la clase COM.  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#31)]  
  
7.  Sobrecargue el método público de la clase base agregando el código siguiente a `MathClass`:  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#32)]  
  
8.  Amplíe la clase heredada agregando el código siguiente a `MathClass`:  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#33)]  
  
 La nueva clase hereda las propiedades de la clase base del objeto COM, sobrecarga un método y define otro método para extender la clase.  
  
#### Para probar la clase heredada  
  
1.  Agregue un botón al formulario de inicio y, a continuación, haga doble clic en él para ver su código.  
  
2.  En el procedimiento del controlador de eventos `Click` del botón, agregue el código siguiente para crear una instancia de `MathClass` y llamar a los métodos sobrecargados:  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/visualbasic/vbvbalrinterop/Class1.vb#34)]  
  
3.  Presione F5 para ejecutar el proyecto.  
  
 Cuando haga clic en el botón del formulario, se llamará primero al método `AddNumbers` con números de tipo de datos `Short` y [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] elegirá el método apropiado en la clase base.  La segunda llamada a `AddNumbers` se dirige al método de sobrecarga de `MathClass`.  La tercera llamada llama al método `SubtractNumbers`, que extiende la clase.  Se establece el valor de la propiedad en la clase base y se muestra dicho valor.  
  
## Pasos siguientes  
 Es posible que haya observado que la función `AddNumbers` sobrecargada parece tener el mismo tipo de datos que el método heredado de la clase base del objeto COM.  Esto se debe a que los argumentos y parámetros del método de la clase base están definidos como enteros de 16 bits en Visual Basic 6.0, pero se exponen como enteros de 16 bits de tipo `Short` en las versiones posteriores de Visual Basic.  La nueva función acepta enteros de 32 bits y sobrecarga la función de la clase base.  
  
 Al trabajar con objetos COM, es importante comprobar el tamaño y los tipos de datos de los parámetros.  Por ejemplo, al utilizar un objeto COM que acepta un objeto de colección de Visual Basic 6.0 como argumento, no puede proporcionar una colección de una versión posterior de Visual Basic.  
  
 Es posible reemplazar propiedades y métodos heredados de clases COM, lo que significa que se puede declarar una propiedad o método local que reemplace una propiedad o método heredado de una clase base COM.  Las reglas para reemplazar propiedades COM heredadas son similares a las reglas para reemplazar otras propiedades y métodos, con las excepciones siguientes:  
  
-   Si reemplaza cualquier propiedad o método heredado de una clase COM, deberá reemplazar todas las demás propiedades y métodos heredados.  
  
-   No es posible reemplazar las propiedades que utilizan parámetros `ByRef`.  
  
## Vea también  
 [Interoperabilidad COM en aplicaciones .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Inherits \(Instrucción\)](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Short \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/short-data-type.md)