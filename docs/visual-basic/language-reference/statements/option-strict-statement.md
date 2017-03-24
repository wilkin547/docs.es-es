---
title: "Option Strict (instrucción) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Strict
- vb.OptionStrict
dev_langs:
- VB
helpviewer_keywords:
- Strict keyword
- Option Strict statement
- conversions, implicit
- late binding
- implicit conversions
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
caps.latest.revision: 49
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
ms.openlocfilehash: 3bf0d4939f24c38392d7ca4764c41d12366067b5
ms.lasthandoff: 03/13/2017

---
# <a name="option-strict-statement"></a>Option Strict Statement
Restringe las conversiones de tipos de datos implícitos a conversiones de ampliación únicamente, no permite el enlace más tarde y no permite tipos implícitos que da como resultado un `Object` tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`On`|Opcional. Permite `Option Strict` comprobación.|  
|`Off`|Opcional. Deshabilita `Option Strict` comprobación.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando `Option Strict On` o `Option Strict` aparece en el archivo, las condiciones siguientes provocar un error en tiempo de compilación:  
  
-   Conversiones de restricción implícitas  
  
-   Enlace en tiempo de ejecución  
  
-   Tipos implícitos que da como resultado un `Object` tipo  
  
> [!NOTE]
>  En las configuraciones de advertencia que se pueden establecer en el [página compilación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic), existen tres valores que corresponden a las tres condiciones que provocan un error en tiempo de compilación. Para obtener información acerca de cómo usar esta configuración, consulte [para establecer configuraciones de advertencia en el IDE](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) más adelante en este tema.  
  
 El `Option Strict Off` instrucción desactiva error y advertencia de comprobación para todas las tres condiciones, incluso si la configuración de IDE asociada que se especifique para activar estos errores o advertencias. El `Option Strict On` instrucción activa error y advertencia comprobando las tres condiciones, incluso si la configuración de IDE asociada que se especifique para desactivar estos errores o advertencias.  
  
 Si utiliza esta opción, el `Option Strict` instrucción debe aparecer antes de cualquier otra instrucción de código en un archivo.  
  
 Al establecer `Option Strict` a `On`, Visual Basic comprueba que se especifican los tipos de datos para todos los elementos de programación. Tipos de datos se pueden especificar explícitamente o especificados mediante la inferencia de tipo local. Especificar los tipos de datos para todos los elementos de programación se recomienda, por los motivos siguientes:  
  
-   Habilita la compatibilidad con IntelliSense para las variables y parámetros. Esto le permite ver sus propiedades y otros miembros a medida que escribe el código.  
  
-   Hace que el compilador realice la comprobación de tipos. Comprobación de tipos ayuda a encontrar las instrucciones que se pueden producir un error en tiempo de ejecución debido a errores de conversión de tipo. También identifica las llamadas a métodos en objetos que no admiten los métodos.  
  
-   Acelera la ejecución del código. Una razón para esto es que si no especifica un tipo de datos para un elemento de programación, el compilador de Visual Basic le asigna el `Object` tipo. Código compilado tendría que realizar conversiones entre `Object` y otros tipos de datos, lo que reduce el rendimiento.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Errores de conversión de restricción implícitas  
 Errores de conversión de restricción implícitas se producen cuando existe una conversión de tipos de datos implícita es una conversión de restricción.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]puede convertir a muchos tipos de datos a otros tipos de datos. Puede producirse pérdida de datos cuando el valor de un tipo de datos se convierte en un tipo de datos que tiene menor precisión o menor capacidad. Si se produce un error en dicha conversión de restricción, se produce un error de tiempo de ejecución. `Option Strict`garantiza la notificación en tiempo de compilación de estas conversiones de restricción para que pueda evitarlas. Para obtener más información, consulte [conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) y [conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Las conversiones que pueden producir errores incluyen conversiones implícitas que se producen en las expresiones. Para obtener más información, vea los temas siguientes:  
  
-   [Operador +](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [Operador +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\ (Operador, Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [/ = (Operador, Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Char (tipo de datos)](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 Al concatenar cadenas utilizando el [aspecto operador](../../../visual-basic/language-reference/operators/concatenation-operator.md), todas las conversiones a las cadenas se consideran de ampliación. Por lo que estas conversiones no generan un error de conversión de restricción implícitas, incluso si `Option Strict` se encuentra en.  
  
 Cuando se llama a un método que tiene un argumento que tiene un tipo de datos diferente del parámetro correspondiente, una conversión de restricción produce un error de tiempo de compilación si `Option Strict` se encuentra en. Puede evitar el error en tiempo de compilación mediante una conversión de ampliación o una conversión explícita.  
  
 Se suprimen los errores de conversión de restricción implícitas en tiempo de compilación para las conversiones de los elementos en una `For Each…Next` colección a la variable de control de bucle. Esto ocurre incluso si `Option Strict` se encuentra en. Para obtener más información, consulte la sección "Conversiones de restricción" en [For Each... Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Errores de enlace en tiempo de ejecución  
 Un objeto se enlaza más tarde cuando se asigna a una propiedad o método de una variable que se declara como de tipo `Object`. Para obtener más información, consulte [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Errores de tipo de objeto implícito  
 Se producen errores de tipo de objeto implícito cuando no puede ser un tipo adecuado para una variable declarada, por lo que un tipo deducido de `Object` se deduce. Esto se produce principalmente cuando se usa un `Dim` instrucción para declarar una variable sin utilizar un `As` cláusula, y `Option Infer` está desactivada. Para obtener más información, consulte [Option Infer instrucción](../../../visual-basic/language-reference/statements/option-infer-statement.md) y [especificación del lenguaje Visual Basic](../../../visual-basic/reference/language-specification.md).  
  
 Para los parámetros de método, el `As` cláusula es opcional si `Option Strict` está desactivada. Sin embargo, si utiliza un parámetro una `As` cláusula, todos deben utilizarlo. Si `Option Strict` está activado, el `As` cláusula es necesaria para cada definición de parámetro.  
  
 Si declara una variable sin utilizar un `As` cláusula y establézcalo en `Nothing`, la variable tiene un tipo de `Object`. En este caso se produce ningún error de tiempo de compilación cuando `Option Strict` en y `Option Infer` en. Un ejemplo de esto es `Dim something = Nothing`.  
  
### <a name="default-data-types-and-values"></a>Tipos de datos y valores predeterminados  
 En la tabla siguiente se describe los resultados de diversas combinaciones de especificar el tipo de datos y el inicializador de un [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|¿Tipo de datos especificado?|¿Inicializador especificado?|Ejemplo|Resultado|  
|---|---|---|---|  
|No|No|`Dim qty`|Si `Option Strict` está desactivado (valor predeterminado), la variable se establece en `Nothing`.<br /><br /> Si `Option Strict` está activado, se produce un error en tiempo de compilación.|  
|No|Sí|`Dim qty = 5`|Si `Option Infer` está activado (valor predeterminado), la variable toma el tipo de datos del inicializador. Consulte [inferencia del tipo Local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está desactivado, la variable toma el tipo de datos de `Object`.<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está activado, se produce un error en tiempo de compilación.|  
|Sí|No|`Dim qty As Integer`|La variable se inicializa con el valor predeterminado del tipo de datos. Para obtener más información, consulte [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Sí|Sí|`Dim qty  As Integer = 5`|Si el tipo de datos del inicializador no es convertible al tipo de datos especificado, se produce un error en tiempo de compilación.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Cuando una instrucción Option Strict no está presente  
 Si el código fuente no contiene una `Option Strict` instrucción, el **Option strict** en el [página compilación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) se utiliza. El **página compilación** tiene una configuración que proporciona control adicional sobre las condiciones que generan un error.  
  
 Si se utiliza el compilador de línea de comandos, puede utilizar el [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) para especificar un valor para la opción del compilador `Option Strict`.  
  
### <a name="to-set-option-strict-in-the-ide"></a>Para establecer Option Strict en el IDE  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
1.  En **el Explorador de soluciones**, seleccione un proyecto. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  En el **compilar** ficha, establezca el valor de la **Option Strict** cuadro.  
  
###  <a name="conditions"></a>Para establecer configuraciones de advertencia en el IDE  
 Cuando se usa el [página compilación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) en lugar de un `Option Strict` instrucción, tiene un control adicional sobre las condiciones que generan errores. El **configuraciones de advertencia** sección de la **página compilación** tiene valores que corresponden a las tres condiciones que provocan un error en tiempo de compilación cuando `Option Strict` se encuentra en. Siguiente es estos valores:  
  
-   **Conversión implícita**  
  
-   **Enlace tardío; la llamada podría fallar en tiempo de ejecución**  
  
-   **Tipo implícito; se supone el objeto**  
  
 Al establecer **Option Strict** a **en**, tres de estas opciones de configuración de la advertencia se establecen en **Error**. Al establecer **Option Strict** a **desactivar**, las tres opciones se establecen en **ninguno**.  
  
 Puede cambiar individualmente cada configuración de advertencia **ninguno**, **advertencia**, o **Error**. Si se establecen las tres opciones de configuración de advertencia en **Error**, `On` aparece en la `Option strict` cuadro. Si se establecen las tres en **ninguno**, `Off` aparece en este cuadro. Para cualquier otra combinación de estas opciones, **(personalizada)** aparece.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Para establecer el valor predeterminado Option Strict para nuevos proyectos  
 Cuando se crea un proyecto, el **Option Strict** en el **compilar** ficha se establece en el **Option Strict** en el **opciones** cuadro de diálogo.  
  
 Para establecer `Option Strict` en este cuadro de diálogo, en la **herramientas** menú, haga clic en **opciones**. En el **opciones** diálogo cuadro, expanda **proyectos y soluciones**y, a continuación, haga clic en **valores predeterminados de VB**. El valor predeterminado inicial de **valores predeterminados de VB** es `Off`.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Para establecer Option Strict en la línea de comandos  
 Incluir el [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) opción del compilador en el **vbc** comando.  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran los errores de tiempo de compilación causados por las conversiones implícitas de tipos que son conversiones de restricción. Esta categoría de errores corresponde a la **conversión implícita** condición en la **página compilación**.  
  
 [!code-vb[VbVbalrStatements&#161;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un error de tiempo de compilación por un enlace más tarde. Esta categoría de errores corresponde a la **Late binding; la llamada podría fallar en tiempo de ejecución** condición en la **página compilación**.  
  
 [!code-vb[VbVbalrStatements&#162;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran errores causados por variables que se declaran con un tipo implícito de `Object`. Esta categoría de errores corresponde a la **tipo implícito; se supone el objeto** condición en la **página compilación**.  
  
 [!code-vb[VbVbalrStatements&#163;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements&#164;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Conversiones de restricción y ampliación](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Página Compilación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)   
 [Option Explicit (instrucción)](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Funciones de conversión de tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Cómo: obtener acceso a miembros de un objeto](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [Expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Enlace tardío en soluciones de Office](https://msdn.microsoft.com/library/3xxe951d)   
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
