---
title: Option Strict Statement (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 1fce65b70c663ca56427122abb604d16fcd029d7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981548"
---
# <a name="option-strict-statement"></a>Option Strict Statement
Restringe las conversiones de tipos de datos implícitos a conversiones de ampliación únicamente, no permite el enlace en tiempo de ejecución y no permite tipos implícitos que da como resultado un `Object` tipo.  
  
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
 Cuando `Option Strict On` o `Option Strict` aparece en el archivo, las siguientes condiciones producir un error en tiempo de compilación:  
  
-   Conversiones de restricción implícitas  
  
-   Enlace en tiempo de ejecución  
  
-   Tipos implícitos que dan como resultado un tipo `Object`  
  
> [!NOTE]
>  En las configuraciones de advertencias que se pueden establecer en el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), hay tres opciones que corresponden a las tres condiciones que producen un error en tiempo de compilación. Para obtener información sobre cómo usar estas opciones, consulte [para establecer configuraciones de advertencias en el IDE](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) más adelante en este tema.  
  
 El `Option Strict Off` instrucción desactiva error y advertencia de comprobación para todas las tres condiciones, incluso si especifica la configuración de IDE asociada para activar estos errores o advertencias. El `Option Strict On` instrucción activa error y advertencia de comprobación para todas las tres condiciones, incluso si especifica la configuración de IDE asociada para desactivar estos errores o advertencias.  
  
 Si usa, la `Option Strict` la instrucción debe aparecer antes que cualquier otra instrucción de código en un archivo.  
  
 Al establecer `Option Strict` a `On`, Visual Basic comprueba que se especifican los tipos de datos para todos los elementos de programación. Tipos de datos se pueden especificar explícitamente o especificados mediante el uso de la inferencia de tipos local. Se recomienda la especificación de tipos de datos para todos los elementos de programación, por las razones siguientes:  
  
-   Habilita la compatibilidad con IntelliSense para las variables y parámetros. Esto le permite ver sus propiedades y otros miembros a medida que escribe código.  
  
-   Permite al compilador que realice la comprobación de tipos. Comprobación de tipos le ayuda a encontrar las instrucciones que se pueden producir un error en tiempo de ejecución debido a errores de conversión de tipo. También identifica las llamadas a métodos en objetos que no admiten esos métodos.  
  
-   Acelera la ejecución del código. Una razón para esto es que si no especifica un tipo de datos para un elemento de programación, el compilador de Visual Basic asigna el `Object` tipo. Código compilado que sea necesario convertir entre `Object` y otros tipos de datos, lo que reduce el rendimiento.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Errores de conversión de restricción implícitas  
 Los errores de conversión de restricción implícita se producen cuando existe una conversión de tipos de datos implícita que es una conversión de restricción.  
  
 Visual Basic puede convertir a muchos tipos de datos en otros tipos de datos. Cuando el valor de un tipo de datos se convierte en un tipo de datos que tiene menos precisión o menor capacidad, puede producirse pérdida de datos. Se produce un error de tiempo de ejecución si se produce un error de este tipo una conversión de restricción. `Option Strict` garantiza la notificación en tiempo de compilación de estas conversiones de restricción para que pueda evitarlas. Para obtener más información, consulte [conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) y [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Las conversiones que pueden causar errores incluyen las conversiones implícitas que se producen en las expresiones. Para obtener más información, vea los temas siguientes:  
  
-   [Operador +](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [Operador +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\ (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [/ = (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Char (tipo de datos)](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 Al concatenar cadenas mediante el uso de la [& operador](../../../visual-basic/language-reference/operators/concatenation-operator.md), todas las conversiones a las cadenas se consideran de ampliación. Para que estas conversiones no genere un error de conversión de restricción implícitas, incluso si `Option Strict` está activado.  
  
 Cuando se llama a un método que tiene un argumento que tiene un tipo de datos diferente del parámetro correspondiente, una conversión de restricción produce un error de tiempo de compilación si `Option Strict` está activado. Puede evitar el error de tiempo de compilación mediante una conversión de ampliación o una conversión explícita.  
  
 Errores de conversión de restricción implícita se suprimen en tiempo de compilación para las conversiones de los elementos de un `For Each…Next` colección a la variable de control de bucle. Esto ocurre incluso si `Option Strict` está activado. Para obtener más información, vea la sección "Narrowing Conversions" en [For Each... Instrucción Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Errores de enlace en tiempo de ejecución  
 Un objeto se enlaza en tiempo de ejecución cuando se asigna a una propiedad o un método de una variable que se declara como variable de tipo `Object`. Para obtener más información, consulte [temprana y enlace tardío](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Errores de tipo de objeto implícito  
 Los errores de tipo de objeto implícito se producen cuando no se puede inferir un tipo adecuado para una variable declarada, por lo que se infiere un tipo de `Object`. Esto se produce principalmente cuando se usa una instrucción `Dim` para declarar una variable sin usar una cláusula `As` y `Option Infer` está desactivado. Para obtener más información, consulte [instrucción Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) y [especificación del lenguaje Visual Basic](../../../visual-basic/reference/language-specification/index.md).  
  
 Para los parámetros de método, el `As` cláusula es opcional si `Option Strict` está desactivada. Sin embargo, si utiliza un parámetro una `As` cláusula, todas ellas deben usarla. Si `Option Strict` está activado, el `As` cláusula es obligatoria para cada definición de parámetro.  
  
 Si declara una variable sin usar un `As` cláusula y establézcalo en `Nothing`, la variable tiene un tipo de `Object`. En este caso se produce ningún error de tiempo de compilación cuando `Option Strict` está activado y `Option Infer` está activado. Un ejemplo de esto es `Dim something = Nothing`.  
  
### <a name="default-data-types-and-values"></a>Tipos de datos y valores predeterminados  
 En la tabla siguiente se describe los resultados de diversas combinaciones de especificar el tipo de datos y un inicializador en una [instrucción Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|¿Tipo de datos especificado?|¿Inicializador especificado?|Ejemplo|Resultado|  
|---|---|---|---|  
|No|No|`Dim qty`|Si `Option Strict` está desactivado (valor predeterminado), la variable se establece en `Nothing`.<br /><br /> Si `Option Strict` está activado, se produce un error en tiempo de compilación.|  
|No|Sí|`Dim qty = 5`|Si `Option Infer` está activado (valor predeterminado), la variable toma el tipo de datos del inicializador. Consulte [inferencia de tipos Local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está desactivado, la variable toma el tipo de datos de `Object`.<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está activado, se produce un error en tiempo de compilación.|  
|Sí|No|`Dim qty As Integer`|La variable se inicializa con el valor predeterminado del tipo de datos. Para obtener más información, consulte [instrucción Dim](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Sí|Sí|`Dim qty  As Integer = 5`|Si el tipo de datos del inicializador no es convertible al tipo de datos especificado, se produce un error en tiempo de compilación.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Cuando una instrucción Option Strict no está presente  
 Si el código fuente no contiene un `Option Strict` instrucción, el **Option strict** en el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) se utiliza. El **página compilación** tiene una configuración que proporciona control adicional sobre las condiciones que generan un error.  
  
 Si usa el compilador de línea de comandos, puede usar el [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) para especificar un valor para la opción del compilador `Option Strict`.  
  
### <a name="to-set-option-strict-in-the-ide"></a>Cómo establecer Option Strict en el IDE  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1.  En el **Explorador de soluciones**, seleccione un proyecto. En el menú **Proyecto**, haga clic en **Propiedades**.  
  
2.  En el **compilar** pestaña, establezca el valor de la **Option Strict** cuadro.  
  
###  <a name="conditions"></a> Para establecer configuraciones de advertencias en el IDE  
 Cuando se usa el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) en lugar de un `Option Strict` instrucción, tenga más control sobre las condiciones que generan errores. El **configuraciones de advertencias** sección de la **página compilación** tiene una configuración que se corresponde con las tres condiciones que producen un error en tiempo de compilación cuando `Option Strict` está activado. Estas opciones son las siguientes:  
  
-   **Conversión implícita**  
  
-   **Enlace en tiempo de ejecución; la llamada podría generar un error en tiempo de ejecución**  
  
-   **Tipo implícito; se supone el objeto**  
  
 Al establecer **Option Strict** en **On**, estos tres valores de configuración de advertencias se establecen en **Error**. Al establecer **Option Strict** en **Off**, las tres opciones se establecen en **None**.  
  
 Puede cambiar individualmente cada valor de configuración de advertencia por **None**, **Warning** o **Error**. Si se establecen las tres opciones de configuración de advertencia en **Error**, `On` aparece en el cuadro `Option strict`. Si se establecen las tres en **None**, `Off` aparece en este cuadro. Para cualquier otra combinación de estas opciones, aparece **(personalizado)**.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Para establecer el valor de Option Strict de forma predeterminada para nuevos proyectos  
 Cuando se crea un proyecto, el **Option Strict** en el **compilar** ficha se establece en el **Option Strict** en el **opciones** cuadro de diálogo.  
  
 Para establecer `Option Strict` en este cuadro de diálogo, en el **herramientas** menú, haga clic en **opciones**. En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, después, haga clic en **Valores predeterminados de VB**. El valor predeterminado inicial de **valores predeterminados de VB** es `Off`.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Para establecer Option Strict en la línea de comandos  
 Incluir el [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) opción del compilador en el **vbc** comando.  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran errores de tiempo de compilación causados por las conversiones implícitas que las conversiones de restricción. Esta categoría de errores que se corresponde con el **conversión implícita** condición en la **página compilación**.  
  
 [!code-vb[VbVbalrStatements#161](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#161)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra un error en tiempo de compilación causado por el enlace en tiempo de ejecución. Esta categoría de errores que se corresponde con el **Late binding; llamada podría generar un error en tiempo de ejecución** condición en la **página compilación**.  
  
 [!code-vb[VbVbalrStatements#162](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#162)]  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran los errores causados por las variables que se declaran con un tipo implícito de `Object`. Esta categoría de errores que se corresponde con el **tipo implícito; se supone el objeto** condición en la **página compilación**.  
  
 [!code-vb[VbVbalrStatements#163](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#163)]  
  
 [!code-vb[VbVbalrStatements#164](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#164)]  
  
## <a name="see-also"></a>Vea también

- [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Página Compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Option Explicit (instrucción)](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Cómo: Obtener acceso a miembros de un objeto](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [Expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Enlace en tiempo de ejecución en las soluciones de Office](/visualstudio/vsto/late-binding-in-office-solutions)
- [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
