---
title: Option Strict Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Strict
- vb.OptionStrict
helpviewer_keywords:
- Strict keyword [Visual Basic]
- Option Strict statement [Visual Basic]
- conversions [Visual Basic], implicit
- late binding [Visual Basic]
- implicit conversions [Visual Basic]
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
caps.latest.revision: "49"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 238f64001b097b86306e0ed9630bd5df2e6a189f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
 Cuando `Option Strict On` o `Option Strict` aparece en el archivo, las condiciones siguientes producen un error de tiempo de compilación:  
  
-   Conversiones de restricción implícitas  
  
-   Enlace en tiempo de ejecución  
  
-   Tipos implícitos que da como resultado un `Object` tipo  
  
> [!NOTE]
>  En las configuraciones de advertencia que se pueden establecer en el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), hay tres opciones que corresponden a las tres condiciones que producen un error en tiempo de compilación. Para obtener información sobre cómo usar esta configuración, consulte [para establecer configuraciones de advertencia en el IDE](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) más adelante en este tema.  
  
 El `Option Strict Off` instrucción desactiva error y advertencia de comprobación para todas las tres condiciones, incluso si la configuración de IDE asociada que se especifique para activar estos errores o advertencias. El `Option Strict On` instrucción activa de error y advertencia de comprobación para todas las tres condiciones, incluso si la configuración de IDE asociada que se especifique para desactivar estos errores o advertencias.  
  
 Si usa, el `Option Strict` la instrucción debe aparecer antes que cualquier otra instrucción de código en un archivo.  
  
 Al establecer `Option Strict` a `On`, Visual Basic comprueba que se especifican los tipos de datos para todos los elementos de programación. Tipos de datos pueden especificados explícitamente o se especifica mediante la inferencia de tipo local. Especificar los tipos de datos para todos los elementos de programación se recomienda, por las razones siguientes:  
  
-   Habilita la compatibilidad con IntelliSense para las variables y parámetros. Esto le permite ver sus propiedades y otros miembros a medida que escribe código.  
  
-   Permite al compilador realizar la comprobación de tipos. Comprobación de tipos ayuda a encontrar las instrucciones que pueden producir un error en tiempo de ejecución debido a errores de conversión de tipo. También se identifican las llamadas a métodos en objetos que no son compatibles con estos métodos.  
  
-   Acelera la ejecución del código. Una razón para esto es que si no especifica un tipo de datos para un elemento de programación, el compilador de Visual Basic le asigna el `Object` tipo. Código compilado que sea necesario convertir entre `Object` y otros tipos de datos, lo que reduce el rendimiento.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Errores de conversión de restricción implícitas  
 Errores de conversión de restricción implícitas se producen cuando existe una conversión de tipos implícita de datos que es una conversión de restricción.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]puede convertir a muchos tipos de datos en otros tipos de datos. Puede producirse una pérdida de datos cuando el valor de un tipo de datos se convierte en un tipo de datos que tiene menor precisión o menor capacidad. Si se produce un error de este tipo una conversión de restricción, se produce un error de tiempo de ejecución. `Option Strict`garantiza la notificación en tiempo de compilación de estas conversiones de restricción para que pueda evitarlas. Para obtener más información, consulte [conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) y [conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Las conversiones que pueden producir errores incluyen conversiones implícitas que se producen en las expresiones. Para obtener más información, vea los temas siguientes:  
  
-   [Operador +](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [Operador +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\ (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [/ = (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Char (tipo de datos)](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 Al concatenar cadenas mediante el uso de la [& operador](../../../visual-basic/language-reference/operators/concatenation-operator.md), todas las conversiones a las cadenas se consideran de ampliación. Por lo que estas conversiones no generan un error de conversión de restricción implícitas, incluso si `Option Strict` se encuentra en.  
  
 Cuando se llama a un método que tiene un argumento que tiene un tipo de datos distinto del parámetro correspondiente, una conversión de restricción produce un error de tiempo de compilación si `Option Strict` se encuentra en. Puede evitar el error de tiempo de compilación mediante una conversión de ampliación o una conversión explícita.  
  
 Errores de conversión de restricción implícitas se suprimen en tiempo de compilación para las conversiones de los elementos en una `For Each…Next` colección a la variable de control de bucle. Esto ocurre incluso si `Option Strict` se encuentra en. Para obtener más información, vea la sección "Conversiones de restricción" en [For Each... Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Errores de enlace en tiempo de ejecución  
 Tiempo de ejecución se enlaza un objeto cuando se asigna a una propiedad o método de una variable que se declara como de tipo `Object`. Para obtener más información, consulte [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Errores de tipo de objeto implícito  
 Se producen errores de tipo de objeto implícito cuando no puede ser un tipo adecuado para una variable declarada, por lo que un tipo deducido de `Object` se deduce. Esto se produce principalmente cuando se usa un `Dim` instrucción para declarar una variable sin utilizar un `As` cláusula, y `Option Infer` está desactivada. Para obtener más información, consulte [Option Infer instrucción](../../../visual-basic/language-reference/statements/option-infer-statement.md) y [especificación del lenguaje Visual Basic](../../../visual-basic/reference/language-specification/index.md).  
  
 Para los parámetros de método, el `As` cláusula es opcional si `Option Strict` está desactivada. Sin embargo, si utiliza un parámetro un `As` cláusula, todas ellas deben usarlo. Si `Option Strict` está activado, el `As` cláusula es necesaria para cada definición de parámetro.  
  
 Si se declara una variable sin utilizar un `As` cláusula y establézcalo en `Nothing`, la variable tiene un tipo de `Object`. En este caso se produce ningún error de tiempo de compilación cuando `Option Strict` se encuentra en y `Option Infer` se encuentra en. Un ejemplo de esto es `Dim something = Nothing`.  
  
### <a name="default-data-types-and-values"></a>Tipos de datos y valores predeterminados  
 En la tabla siguiente se describe los resultados de diversas combinaciones de especificar el tipo de datos y el inicializador en una [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|¿Tipo de datos especificado?|¿Inicializador especificado?|Ejemplo|Resultado|  
|---|---|---|---|  
|No|No|`Dim qty`|Si `Option Strict` está desactivado (valor predeterminado), la variable se establece en `Nothing`.<br /><br /> Si `Option Strict` está activado, se produce un error en tiempo de compilación.|  
|No|Sí|`Dim qty = 5`|Si `Option Infer` está activado (valor predeterminado), la variable toma el tipo de datos del inicializador. Vea [inferencia de tipo Local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está desactivado, la variable toma el tipo de datos de `Object`.<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está activado, se produce un error en tiempo de compilación.|  
|Sí|No|`Dim qty As Integer`|La variable se inicializa con el valor predeterminado del tipo de datos. Para obtener más información, consulte [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Sí|Sí|`Dim qty  As Integer = 5`|Si el tipo de datos del inicializador no es convertible al tipo de datos especificado, se produce un error en tiempo de compilación.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Cuando una instrucción Option Strict no está presente  
 Si el código fuente no contiene un `Option Strict` (instrucción), el **Option strict** en el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) se utiliza. El **página compilación** tiene una configuración que proporciona un mayor control sobre las condiciones que generan un error.  
  
 Si está utilizando el compilador de línea de comandos, puede usar el [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) opción del compilador para especificar un valor para `Option Strict`.  
  
### <a name="to-set-option-strict-in-the-ide"></a>Para establecer Option Strict en el IDE  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1.  En el **Explorador de soluciones**, seleccione un proyecto. En el menú **Proyecto**, haga clic en **Propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  En el **compilar** pestaña, establezca el valor de la **Option Strict** cuadro.  
  
###  <a name="conditions"></a>Para establecer configuraciones de advertencia en el IDE  
 Cuando se usa el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) en lugar de un `Option Strict` (instrucción), tiene un control adicional sobre las condiciones que generan errores. El **configuraciones de advertencia** sección de la **página compilación** tiene una configuración que se corresponde con las tres condiciones que producen un error en tiempo de compilación cuando `Option Strict` se encuentra en. Estas opciones son las siguientes:  
  
-   **Conversión implícita**  
  
-   **Enlace en tiempo de ejecución; la llamada podría fallar en tiempo de ejecución**  
  
-   **Tipo implícito; se supone el objeto**  
  
 Al establecer **Option Strict** a **en**, se establecen las tres de estos valores de configuración de la advertencia en **Error**. Al establecer **Option Strict** a **desactivar**, las tres opciones se establecen en **ninguno**.  
  
 Puede cambiar individualmente cada configuración de advertencia si se establece en **ninguno**, **advertencia**, o **Error**. Si se establecen las tres opciones de configuración de advertencia en **Error**, `On` aparece en la `Option strict` cuadro. Si se establecen las tres en **ninguno**, `Off` aparece en este cuadro. Para cualquier otra combinación de estas opciones, **(personalizada)** aparece.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Para establecer el valor predeterminado Option Strict para los nuevos proyectos  
 Cuando se crea un proyecto, el **Option Strict** en el **compilar** pestaña está establecida en el **Option Strict** en el **opciones** cuadro de diálogo.  
  
 Para establecer `Option Strict` en este cuadro de diálogo, en la **herramientas** menú, haga clic en **opciones**. En el **opciones** cuadro de diálogo, expanda **proyectos y soluciones**y, a continuación, haga clic en **valores predeterminados de VB**. El valor predeterminado inicial de **valores predeterminados de VB** es `Off`.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Para establecer Option Strict en la línea de comandos  
 Incluir el [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) opción del compilador en el **vbc** comando.  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran errores de tiempo de compilación causados por las conversiones implícitas de tipos que son conversiones de restricción. Esta categoría de errores que se corresponde con el **conversión implícita** condición en la **página compilación**.  
  
 [!code-vb[VbVbalrStatements#161](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un error en tiempo de compilación causado por el enlace más tarde. Esta categoría de errores que se corresponde con el **Late enlace; la llamada podría fallar en tiempo de ejecución** condición en la **página compilación**.  
  
 [!code-vb[VbVbalrStatements#162](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran errores causados por las variables que se declaran con un tipo implícito de `Object`. Esta categoría de errores que se corresponde con el **tipos implícita; se supone el objeto** condición en la **página compilación**.  
  
 [!code-vb[VbVbalrStatements#163](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#164](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Página Compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [Option Explicit (instrucción)](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Obtener acceso a los miembros de un objeto](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)  
 [Expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Enlace en tiempo de ejecución en las soluciones de Office](https://msdn.microsoft.com/library/3xxe951d)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
