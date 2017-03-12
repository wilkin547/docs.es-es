---
title: "Objetos y clases de Visual Basic | Microsoft Docs"
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
  - "clases [Visual Basic]"
  - "objetos [Visual Basic]"
ms.assetid: c68c5752-1006-46e1-975a-6717b62a42fc
caps.latest.revision: 26
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 26
---
# Objetos y clases de Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un *objeto* es una combinación de código y datos que puede tratarse como una unidad.  Un objeto puede ser una porción de una aplicación, como un control o un formulario.  Una aplicación entera también puede ser un objeto.  
  
 Cuando se crea una aplicación en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], se trabaja constantemente con objetos.  Se pueden usar los objetos proporcionados por [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], como controles, formularios y objetos de acceso a datos.  También se pueden usar los objetos de otras aplicaciones en la aplicación de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Incluso pueden crearse objetos propios y agregarles propiedades y métodos adicionales.  Los objetos actúan como bloques de creación prefabricados para programas: permiten escribir una porción de código y utilizarla una y otra vez.  
  
 Este tema describe los objetos de forma detallada.  
  
## Objetos y clases  
 Cada objeto de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] está definido por una *clase*.  Una clase describe las variables, propiedades, procedimientos y eventos de un objeto.  Los objetos son instancias de clases; pueden crearse tantos objetos como sean necesarios una vez que se defina una clase.  
  
 Para comprender la relación entre un objeto y su clase, piense en los moldes de hacer galletas y en las galletas.  El molde es la clase.  Define las características de cada galleta, por ejemplo, el tamaño y la forma.  La clase se utiliza para crear objetos.  Los objetos son las galletas.  
  
 Debe crear un objeto antes de poder tener acceso a sus miembros.  
  
#### Para crear un objeto a partir de una clase  
  
1.  Determine en qué clase desea crear un objeto.  
  
2.  Escriba [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md) para crear una variable a la que puede asignar una instancia de clase.  La variable debe ser del tipo de la clase deseada.  
  
    ```  
  
    Dim nextCustomer As customer   
    ```  
  
3.  Agregue la palabra clave [New \(Operador\)](../../../../visual-basic/language-reference/operators/new-operator.md) para inicializar la variable a una nueva instancia de la clase.  
  
    ```  
    Dim nextCustomer As New customer  
    ```  
  
4.  Puede tener acceso a los miembros de la clase ahora a través de la variable de objeto.  
  
    ```  
  
    nextCustomer.accountNumber = lastAccountNumber + 1  
    ```  
  
> [!NOTE]
>  Siempre que sea posible, debe declarar la variable para que sea del tipo de clase que piensa asignarle.  Esto se llama *enlace en tiempo de compilación*.  Si no conoce el tipo de clase en el tiempo de compilación, puede invocar el *enlace en tiempo de ejecución* declarando la variable para que sea [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md).  Sin embargo, el enlace en tiempo de ejecución puede ralentizar el rendimiento y limitar el acceso a los miembros del objeto en tiempo de ejecución.  Para obtener más información, vea [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md).  
  
### Varias instancias  
 Los objetos recientemente creados a partir de una clase son a menudo idénticos.  Una vez que existen como objetos individuales no obstante, sus variables y propiedades se pueden cambiar independientemente de las demás instancias.  Por ejemplo, si agrega tres casillas a un formulario, cada objeto de botón de casilla es una instancia de la clase <xref:System.Windows.Forms.CheckBox>.  Los objetos <xref:System.Windows.Forms.CheckBox> individuales comparten un conjunto de características y funciones comunes \(propiedades, variables, procedimientos y eventos\) definidos por la clase.  No obstante, cada uno tiene su propio nombre, puede habilitarse y deshabilitarse por separado, y puede colocarse en una ubicación diferente en el formulario.  
  
## Miembros de objetos  
 Un objeto es un elemento de una aplicación, que representa una *instancia* de una clase.  Campos, propiedades, métodos y eventos son los bloques de creación básicos de los objetos y constituyen sus *miembros*.  
  
### Acceso a miembros  
 Tiene acceso a un miembro de un objeto especificando, en orden, el nombre de la variable de objeto, un punto \(`.`\) y el nombre del miembro.  En el siguiente ejemplo se establece la propiedad <xref:System.Windows.Forms.Control.Text%2A> de un objeto <xref:System.Windows.Forms.Label>.  
  
```  
warningLabel.Text = "Data not saved"  
```  
  
#### Lista de miembros de IntelliSense  
 IntelliSense lista los miembros de una clase cuando invoca su opción Lista de miembros, por ejemplo, cuando escribe un punto \(`.`\) como un operador de acceso a miembros.  Si escribe el punto después del nombre de una variable declarada como una instancia de esa clase, IntelliSense muestra todos los miembros de instancias y ninguno de los miembros compartidos.  Si escribe el punto después del nombre de clase, IntelliSense lista todos los miembros compartidos y ninguno de los miembros de instancias.  Para obtener más información, vea [Utilizar IntelliSense](/visual-studio/ide/using-intellisense).  
  
### Campos y propiedades  
 *Campos* y *propiedades* representan información almacenada en un objeto.  Recupera y establece los valores con instrucciones de asignación de la misma manera que recupera y establece variables locales en un procedimiento.  En el siguiente ejemplo se recupera la propiedad <xref:System.Windows.Forms.Control.Width%2A> y se establece la propiedad <xref:System.Windows.Forms.Control.ForeColor%2A> de un objeto <xref:System.Windows.Forms.Label>.  
  
```  
Dim warningWidth As Integer = warningLabel.Width  
warningLabel.ForeColor = System.Drawing.Color.Red  
```  
  
 Observe que un campo se llama también *variable miembro*.  
  
 Utilice procedimientos de propiedad cuando:  
  
-   Necesite controlar cuándo y cómo se establece o recupera un valor.  
  
-   La propiedad tenga un conjunto de valores bien definidos que no necesiten validación.  
  
-   El establecimiento del valor genera algún cambio perceptible en el estado del objeto, como una propiedad `IsVisible`.  
  
-   El establecimiento de la propiedad ocasione cambios en otras variables internas o en los valores de otras propiedades.  
  
-   Deban ejecutarse un conjunto de pasos antes de poder establecer o recuperar la propiedad.  
  
 Utilice campos cuando:  
  
-   El valor sea de un tipo de autovalidación.  Por ejemplo, si un valor distinto de `True` o `False` se asigna a una variable `Boolean`, se produce un error o una conversión de datos automática.  
  
-   Sea válido cualquier valor del intervalo admitido por el tipo de datos.  Esto es verdadero en muchas propiedades de tipo `Single` o `Double`.  
  
-   La propiedad sea un tipo de datos `String` y no existan restricciones en cuanto al tamaño o al valor de la cadena.  
  
-   Para obtener más información, vea [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md).  
  
### Métodos  
 Un *método* es una acción que un objeto puede realizar.  Por ejemplo, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> es un método del objeto <xref:System.Windows.Forms.ComboBox> que agrega una nueva entrada a un cuadro combinado.  
  
 En el siguiente ejemplo se muestra el método <xref:System.Windows.Forms.Timer.Start%2A> de un objeto <xref:System.Windows.Forms.Timer>.  
  
```  
Dim safetyTimer As New System.Windows.Forms.Timer  
safetyTimer.Start()  
```  
  
 Observe que un método es simplemente un *procedimiento* expuesto por un objeto.  
  
 Para obtener más información, vea [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md).  
  
### Eventos  
 Un evento es una acción que un objeto reconoce, como hacer clic con el mouse o presionar una tecla, y para el que puede escribir código para responder.  Los eventos se producen como consecuencia de una acción del usuario o de código de programa, o bien pueden ser generados por el sistema.  Se dice que el código que señala un evento *provoca* el evento y que el código que responde a él lo *controla*.  
  
 También puede desarrollar eventos personalizados propios para que los generen sus objetos y los controlen otros objetos.  Para obtener más información, vea [Eventos](../../../../visual-basic/programming-guide/language-features/events/events.md).  
  
### Miembros de instancias y miembros compartidos  
 Cuando crea un objeto a partir de una clase, el resultado es una instancia de esa clase.  Los miembros que no están declarados con la palabra clave [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) son *miembros de instancias* que pertenecen estrictamente a esta instancia en particular.  Un miembro de instancia en una instancia es independiente del mismo miembro en otra instancia de la misma clase.  Por ejemplo, una variable miembro de la instancia puede tener valores diferentes en instancias diferentes.  
  
 Los miembros declarados con la palabra clave `Shared` son *miembros compartidos* que pertenecen a la clase en su conjunto y no a una instancia determinada.  Un miembro compartido sólo existe una vez, independientemente de las instancias de su clase que pueda crear o incluso si no crea ninguna.  Por ejemplo, una variable miembro compartida tiene sólo un valor que está disponible para todo el código que pueda tener acceso a la clase.  
  
#### Tener acceso a miembros no compartidos  
  
###### Para tener acceso a un miembro no compartido de un objeto  
  
1.  Asegúrese de que el objeto se ha creado a partir de su clase y se ha asignado a una variable de objeto.  
  
    ```  
    Dim secondForm As New System.Windows.Forms.Form  
    ```  
  
2.  En la instrucción que tiene acceso al miembro, agregue detrás del nombre de la variable de objeto el *operador de acceso a miembros* \(`.`\) y, a continuación, el nombre del miembro.  
  
    ```  
    secondForm.Show()  
    ```  
  
#### Tener acceso a miembros compartidos  
  
###### Para tener acceso a un miembro compartido de un objeto  
  
-   Agregue detrás del nombre de clase el *operador de acceso a miembros* \(`.`\) y, a continuación, el nombre del miembro.  Siempre debe tener acceso a un miembro `Shared` del objeto directamente a través del nombre de clase.  
  
    ```  
    MsgBox("This computer is called " & Environment.MachineName)  
    ```  
  
-   Si ya ha creado un objeto a partir de la clase, puede tener acceso a un miembro `Shared` alternativamente a través de la variable del objeto.  
  
### Diferencias entre clases y módulos  
 La diferencia principal entre clases y módulos consiste en que pueden crearse instancias de clases como objetos pero no de módulos.  Como sólo existe una copia de los datos de un módulo estándar, cuando una parte del programa cambia una variable pública en un módulo estándar, cualquier otra parte del programa obtendrá el mismo valor si lee luego esa variable.  En comparación, los datos de objeto existen individualmente para cada objeto con instancias.  Otra distinción es que, a diferencia de los módulos estándar, las clases pueden implementar interfaces.  
  
> [!NOTE]
>  Cuando el modificador `Shared` se aplica a un miembro de clase, está asociado con la propia clase en lugar de con una instancia determinada de la clase.  Se tiene acceso directo al miembro mediante el nombre de clase, de la misma manera que se tiene acceso a los miembros de módulos.  
  
 Las clases y los módulos también emplean ámbitos diferentes para sus miembros.  Los miembros definidos dentro de una clase tienen el ámbito de una instancia específica de la clase y sólo existen mientras dure el objeto.  Para tener acceso a los miembros de clases desde el exterior de una clase, debe utilizar los nombres completos con el formato *Objeto*.*Miembro*.  
  
 Por otro lado, los miembros declarados dentro de un módulo son de manera predeterminada accesibles públicamente y se puede obtener acceso a ellos mediante cualquier código que tenga acceso al módulo.  Esto significa que las variables en un módulo estándar son de hecho variables globales porque son visibles desde cualquier parte del proyecto y existen durante toda la vida útil del programa.  
  
## Reutilizar clases y objetos  
 Los objetos permiten declarar variables y procedimientos una vez y utilizarlos siempre que sean necesarios.  Por ejemplo, si desea agregar un corrector ortográfico a una aplicación, puede definir todas las variables y funciones auxiliares para proporcionar funcionalidad de corrección ortográfica.  Si crea el corrector ortográfico como una clase, puede volver a utilizarlo en otras aplicaciones mediante la inclusión de una referencia en el ensamblado compilado.  Aún mejor, tal vez pueda ahorrarse trabajo mediante el uso de una clase de corrector ortográfico que otra persona ya haya desarrollado.  
  
 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] proporciona muchos ejemplos de componentes que están disponibles para su uso.  En el siguiente ejemplo, se utiliza la clase <xref:System.TimeZone> en el espacio de nombres <xref:System>.  <xref:System.TimeZone> proporciona miembros que permiten recuperar información acerca de la zona horaria del sistema del equipo actual.  
  
```  
Public Sub examineTimeZone()  
    Dim tz As System.TimeZone = System.TimeZone.CurrentTimeZone  
    Dim s As String = "Current time zone is "  
    s &= CStr(tz.GetUtcOffset(Now).Hours) & " hours and "  
    s &= CStr(tz.GetUtcOffset(Now).Minutes) & " minutes "  
    s &= "different from UTC (coordinated universal time)"  
    s &= vbCrLf & "and is currently "  
    If tz.IsDaylightSavingTime(Now) = False Then s &= "not "  
    s &= "on ""summer time""."  
    MsgBox(s)  
End Sub  
```  
  
 En el ejemplo anterior, la primera [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md) declara una variable de objeto de tipo <xref:System.TimeZone> y le asigna un objeto <xref:System.TimeZone> devuelto por la propiedad <xref:System.TimeZone.CurrentTimeZone%2A>.  
  
## Relaciones entre objetos  
 Los objetos pueden relacionarse entre sí de varias maneras.  Los tipos principales de relación son *jerárquicos* y *contención*.  
  
### Relación jerárquica  
 Cuando las clases se derivan de las clases más fundamentales, se dice que tienen una *relación jerárquica*.  Las jerarquías de clases son útiles cuando se describen elementos que constituyen un subtipo de una clase más general.  
  
 En el ejemplo siguiente, suponga que desea definir un tipo especial de <xref:System.Windows.Forms.Button> que se comporta como una clase <xref:System.Windows.Forms.Button> normal pero también expone un método que invierte los colores de primer plano y de fondo.  
  
##### Para definir una clase derivada de una clase existente  
  
1.  Utilice [Class \(Instrucción\)](../../../../visual-basic/language-reference/statements/class-statement.md) para definir una clase a partir de la cual crea el objeto que necesita.  
  
     `Public Class reversibleButton`  
  
     Asegúrese de que sigue una instrucción `End Class` después de la última línea de código de la clase.  De manera predeterminada, el entorno de desarrollo integrado \(IDE\) genera automáticamente `End Class` cuando escribe una instrucción `Class`.  
  
2.  Agregue [Inherits \(Instrucción\)](../../../../visual-basic/language-reference/statements/inherits-statement.md) inmediatamente después de la instrucción `Class`.  Especifique la clase de la que se deriva su nueva clase.  
  
     `Inherits System.Windows.Forms.Button`  
  
     Su nueva clase hereda todos los miembros definidos por la clase base.  
  
3.  Agregue el código para los miembros adicionales que expone la clase derivada.  Por ejemplo, puede agregar un método `reverseColors` y su clase derivada podría aparecer del modo siguiente:  
  
    ```  
    Public Class reversibleButton  
        Inherits System.Windows.Forms.Button  
        Public Sub reverseColors()   
            Dim saveColor As System.Drawing.Color = Me.BackColor  
            Me.BackColor = Me.ForeColor  
            Me.ForeColor = saveColor  
        End Sub  
    End Class   
    ```  
  
     Si crea un objeto a partir de la clase `reversibleButton`, puede tener acceso a todos los miembros de la clase <xref:System.Windows.Forms.Button>, así como al método `reverseColors` y a cualquier otro miembro nuevo que define en `reversibleButton`.  
  
 Las clases derivadas heredan miembros de la clase en la que se basan, lo que permite agregar complejidad a medida que se progresa en una jerarquía de clases.  Para obtener más información, vea [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
#### Compilar el código  
 Asegúrese de que el compilador puede tener acceso a la clase de la que piensa hacer derivar su nueva clase.  Esto podría significar la calificación completa de su nombre, como en el ejemplo anterior, o la identificación del espacio de nombres en [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  Si la clase está en un proyecto diferente, es posible que necesite agregar una referencia a ese proyecto.  Para obtener más información, vea [Administrar referencias en un proyecto](/visual-studio/ide/managing-references-in-a-project).  
  
### Relación de contención  
 Otra manera en que se pueden relacionar objetos es una *relación de contención*.  Los objetos contenedores encapsulan lógicamente otros objetos.  Por ejemplo, el objeto <xref:System.OperatingSystem> contiene lógicamente un objeto <xref:System.Version> que vuelve a través de su propiedad <xref:System.OperatingSystem.Version%2A>.  Observe que el objeto contenedor no contiene ningún otro objeto físicamente.  
  
#### Colecciones  
 Un tipo de contención de objetos particular lo representan las *colecciones*.  Las colecciones son grupos de objetos similares que se pueden enumerar.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] admite una sintaxis concreta en la [For Each...Next \(Instrucción\)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) que permite iterar por los elementos de una colección.  Además, las colecciones suelen permitir el uso de <xref:Microsoft.VisualBasic.Collection.Item%2A> para recuperar elementos mediante su índice o asociándolos con una cadena única.  Las colecciones pueden ser más fáciles de utilizar que las matrices puesto que permiten agregar o quitar elementos sin utilizar índices.  Debido a su facilidad de uso, las colecciones se utilizan frecuentemente para almacenar formularios y controles.  
  
## Temas relacionados  
 [Tutorial: Definir clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)  
 Proporciona una descripción paso a paso de cómo crear una clase.  
  
 [Propiedades y métodos sobrecargados](../../../../visual-basic/programming-guide/language-features/objects-and-classes/overloaded-properties-and-methods.md)  
 Propiedades y métodos sobrecargados  
  
 [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 Se describen los modificadores de herencia, el reemplazo de propiedades y métodos, MyClass y MyBase.  
  
 [Duración de los objetos: cómo se crean y destruyen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 Explica cómo se crean y destruyen las instancias de clases.  
  
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 Describe cómo crear y usar tipos anónimos, que permiten crear objetos sin escribir una definición de clase para el tipo de datos.  
  
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 Explica los inicializadores de objeto, que se usan para crear instancias de tipos con nombre y anónimos mediante una sola expresión.  
  
 [Cómo: Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 Explica cómo deducir tipos y nombres de propiedad en las declaraciones de tipos anónimos.  Proporciona ejemplos de inferencias correctas e incorrectas.