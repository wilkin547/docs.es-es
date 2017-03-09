---
title: "Option Strict (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Strict"
  - "vb.OptionStrict"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conversiones, implícita"
  - "conversiones implícitas"
  - "enlace tardío"
  - "Option Strict (instrucción)"
  - "Strict (palabra clave)"
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
caps.latest.revision: 49
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 49
---
# Option Strict (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Restringe las conversiones de tipos de datos implícitas a solo conversiones de ampliación, impide el enlace en tiempo de ejecución y deniega el uso de tipos implícitos que dan como resultado un tipo `Object`.  
  
## Sintaxis  
  
```  
Option Strict { On | Off }  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`On`|Opcional.  Habilita la comprobación `Option Strict`.|  
|`Off`|Opcional.  Deshabilita la comprobación `Option Strict`.|  
  
## Comentarios  
 Cuando `Option Strict On` u `Option Strict` aparecen en un archivo, las condiciones siguientes producen un error en tiempo de compilación:  
  
-   Conversiones de restricción implícitas  
  
-   Enlace en tiempo de ejecución  
  
-   Tipo implícito que da como resultado un tipo `Object`  
  
> [!NOTE]
>  En la configuración de advertencias que se puede establecer en [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic), hay tres valores que corresponden a las tres condiciones que producen un error en tiempo de compilación.  Para obtener información sobre cómo utilizar estas opciones de configuración, vea [Para establecer la configuración de advertencias en el IDE](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) más adelante en este tema.  
  
 La instrucción `Option Strict Off` desactiva la comprobación de errores y advertencias para las tres condiciones, aunque la configuración asociada del IDE especifique activar estos errores o advertencias.  La instrucción de `Option Strict On` gira el error y la advertencia que comprueban para ver si hay tres condiciones, aunque los valores asociados del IDE especifican para desactivar estos errores o advertencias.  
  
 Si se utiliza, la instrucción `Option Strict` tiene que aparecer antes que cualquier otra instrucción de código en un archivo.  
  
 Cuando se `Option Strict` establecido en `On`, comprobaciones de Visual Basic que especifican los tipos de datos para todos los elementos de programación.  Los tipos de datos pueden especificar explícitamente, o especificar mediante la inferencia de tipo de variable local.  Especificar los tipos de datos para todos los elementos de programación se recomienda, por las siguientes razones:  
  
-   Habilita la compatibilidad con IntelliSense® para las variables y los parámetros.  Esto le permite ver las propiedades de las variables y otros miembros a medida que escribe el código.  
  
-   Permite que el compilador realice la comprobación de tipos.  La comprobación de tipos le ayuda a encontrar instrucciones que pueden producir errores en tiempo de ejecución debido a errores de conversión de tipos.  También identifica llamadas a métodos en objetos que no admiten dichos métodos.  
  
-   Acelera la ejecución de código.  Una razón para esto es que si no especifica un tipo de datos para un elemento de programación, el compilador de Visual Basic le asigna el tipo de `Object` .  El código compilado tendría que realizar conversiones en ambos sentidos entre `Object` y otros tipos de datos, lo que reduce el rendimiento.  
  
## Errores implícitos de conversión de restricción  
 Se producen errores implícitos de la conversión de restricción cuando hay una conversión de tipo de datos implícita que es una conversión de restricción.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] puede convertir numerosos tipos de datos en otros distintos.  Sin embargo, se pueden perder datos cuando el valor de un tipo de datos se convierte en un tipo de datos con menor precisión o menor capacidad.  Un error en tiempo de ejecución se produce si se produce un error en este tipo de conversión de restricción.  `Option Strict` asegura la notificación del tiempo de compilación de estas conversiones de restricción para que pueda evitarlas.  Para obtener más información, vea [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) y [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Entre las conversiones que pueden producir errores se incluyen las conversiones implícitas que se producen en las expresiones.  Para obtener más información, vea los temas siguientes:  
  
-   [\+ \(Operador\)](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [\+\= \(Operador\)](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\\ \(Operador\)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [\/\= \(Operador\)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Char \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 Cuando se concatenan cadenas utilizando el [& \(Operador\)](../../../visual-basic/language-reference/operators/concatenation-operator.md), se considera que todas las conversiones en cadenas son de ampliación.  Así, estas conversiones no generan un error implícito de la conversión de restricción, aunque `Option Strict` esté activada.  
  
 Cuando se llama a un método que tiene un argumento con un tipo de datos distinto del parámetro correspondiente, una conversión de restricción causa un error en tiempo de compilación si `Option Strict` está activada.  El error en tiempo de compilación se puede evitar mediante una conversión de ampliación o una conversión explícita.  
  
 Los errores implícitos de la conversión de restricción se suprimen en tiempo de compilación para las conversiones de elementos de una colección `For Each…Next` a la variable de control de bucle.  Esto ocurre incluso cuando `Option Strict` está activada.  Para obtener más información y ejemplos, consulte la sección "Conversiones de restricción" en [For Each...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## Errores de enlace en tiempo de ejecución  
 Un objeto se enlaza en tiempo de ejecución cuando se asigna a una propiedad o método de una variable que se declara de tipo `Object`.  Para obtener más información, vea [Enlace en tiempo de compilación y en tiempo de ejecución](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md).  
  
## Errores implícitos del tipo de objeto  
 Los errores implícitos del tipo de objeto se producen cuando no se puede deducir un tipo adecuado para una variable declarada, por lo que se deduce un tipo `Object`.  Esto se produce principalmente cuando se usa una instrucción `Dim` para declarar una variable sin usar una cláusula `As` y `Option Infer` está desactivada.  Para obtener más información, vea [Option Infer \(instrucción\)](../../../visual-basic/language-reference/statements/option-infer-statement.md) y [Especificación del lenguaje de Visual Basic](../../../visual-basic/reference/language-specification.md).  
  
 Para los parámetros de método, la cláusula `As` es opcional si `Option Strict` está desactivada.  Sin embargo, si un parámetro utiliza una cláusula `As`, deberán utilizarla todos ellos.  Si `Option Strict` está activado, la cláusula `As` es obligatoria en todas las definiciones de parámetros.  
  
 Si se declara una variable sin usar una cláusula `As` y se establece en `Nothing`, el tipo de la variable es `Object`.  En este caso, no se produce ningún error en tiempo de compilación si `Option Strict` y `Option Infer` están activadas.  Un ejemplo de esto es `Dim something = Nothing`.  
  
### Valores y tipos de datos predeterminados  
 La tabla siguiente describe los resultados de varias combinaciones de especificar el tipo de datos y el inicializador en una [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|||||  
|-|-|-|-|  
|¿Tipo de datos especificado?|¿Inicializador especificado?|Ejemplo|Resultado|  
|No|No|`Dim qty`|Si `Option Strict` está desactivada \(el valor predeterminado\), la variable se establece en `Nothing`.<br /><br /> Si `Option Strict` está activada, se produce un error en tiempo de compilación.|  
|No|Sí|`Dim qty = 5`|Si `Option Infer` está activada \(el valor predeterminado\), la variable toma el tipo de datos del inicializador.  Vea [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Si `Option Infer` y `Option Strict` están desactivadas, la variable toma el tipo de datos de `Object`.<br /><br /> Si `Option Infer` está desactivada y `Option Strict` está activada, se produce un error en tiempo de compilación.|  
|Sí|No|`Dim qty As Integer`|La variable se inicializa con el valor predeterminado para el tipo de datos.  Para obtener más información, vea [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Sí|Sí|`Dim qty  As Integer = 5`|Si el tipo de datos del inicializador no es convertible al tipo de datos especificado, se produce un error en tiempo de compilación.|  
  
## Cuando no existe una instrucción Option Strict  
 Si el código fuente no contiene una instrucción `Option Strict`, se utiliza el valor de **Option Strict** en [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic).  La página **Compilación** incluye valores que proporcionan un control adicional sobre las condiciones que generan un error.  
  
 Si está usando el compilador de la línea de comandos, puede usar la opción del compilador [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) a fin de especificar una configuración para `Option Strict`.  
  
### Para establecer Option Strict en el IDE  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
1.  En el **Explorador de soluciones**, seleccione un proyecto.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  En la pestaña **Compilar**, establezca el valor en el cuadro **Option Strict**.  
  
###  <a name="conditions"></a> Para establecer la configuración de advertencias en el IDE  
 Cuando se utiliza [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic) en lugar de una instrucción `Option Strict`, tiene un control adicional sobre las condiciones que generan errores.  La sección **Configuración de advertencias** de la página **Compilación** tiene valores correspondientes a las tres condiciones que producen un error en tiempo de compilación si `Option Strict` se establece en On.  A continuación se muestran estos valores:  
  
-   **Conversión implícita**  
  
-   **Enlace en tiempo de ejecución; la llamada podría dar error en tiempo de ejecución**  
  
-   **Tipo implícito; se asume el objeto**  
  
 Al establecer **Option Strict** en **On**, los tres valores de configuración de advertencias se establecen en **Error**.  Al establecer **Option Strict** en **Off**, los tres valores se establecen en **None**.  
  
 Puede cambiar individualmente cada valor de configuración de advertencias a **Ninguno**, **Advertencia** o **Error**.  Si la tres configuración de advertencias se establecen en **Error**, `On` aparece en el cuadro `Option strict`.  Si los tres se establecen en **None**, `Off` aparece en este cuadro.  Para cualquier otra combinación de estos valores, aparece **\(personalizado\)**.  
  
### Para establecer la configuración predeterminada Option Strict para nuevos proyectos  
 Cuando se crea un proyecto, el valor de **Option Strict** en la pestaña **Compilar** se establece en el valor de **Option Strict** del cuadro de diálogo **Opciones**.  
  
 Para establecer `Option Strict` en este cuadro de diálogo, en el menú **Herramientas**, haga clic en **Opciones**.  En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, a continuación, haga clic en **Valores predeterminados de VB**.  El valor predeterminado inicial de **Valores predeterminados de VB** es `Off`.  
  
### Para establecer Option Strict en la línea de comandos  
 Incluya la opción del compilador [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) en el comando **vbc**.  
  
## Ejemplo  
 En los ejemplos siguientes se muestran errores de compilación producidos por conversiones de tipos implícitas que son conversiones de restricción.  Esta categoría de errores corresponde a la condición **Conversión implícita** en la página **Compilación**.  
  
 [!code-vb[VbVbalrStatements#161](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/option-strict-statement_1.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un error de tiempo de compilación causado por el enlace en tiempo de ejecución.  Esta categoría de errores corresponde a la condición **Enlace en tiempo de ejecución; la llamada podría dar error en tiempo de ejecución** en la página **Compilación**.  
  
 [!code-vb[VbVbalrStatements#162](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/option-strict-statement_2.vb)]  
  
## Ejemplo  
 En los ejemplos siguientes se muestran errores producidos por variables declaradas con un tipo implícito de `Object`.  Esta categoría de errores corresponde a la condición **Tipo implícito; se supone el objeto** en la página **Compilación**.  
  
 [!code-vb[VbVbalrStatements#163](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#164](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/option-strict-statement_4.vb)]  
  
## Vea también  
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)   
 [Option Explicit \(Instrucción\)](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Cómo: Obtener acceso a los miembros de un objeto](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [Expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Enlace en tiempo de ejecución en las soluciones de Office](/office-dev/office-dev/late-binding-in-office-solutions)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [Valores predeterminados de Visual Basic, Proyectos, Opciones \(Cuadro de diálogo\)](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)