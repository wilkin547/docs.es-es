---
title: 'Tutorial: Llamar a las API de Windows (Visual Basic) | Documentos de Microsoft'
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
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls, walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement, declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
caps.latest.revision: 20
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
ms.openlocfilehash: 5001ccebb0a5b8cadd4e856342601506cf1d033f
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Tutorial: Llamar a las API de Windows (Visual Basic)
Las API de Windows son bibliotecas de vínculos dinámicos (DLL) que forman parte del sistema operativo Windows. Usarlos para realizar tareas cuando resulta difícil escribir procedimientos equivalentes. Por ejemplo, Windows proporciona una función denominada `FlashWindowEx` que permite que la barra de título de una aplicación alterne entre claras y oscuras.  
  
 La ventaja de usar las API de Windows en el código es que pueden ahorrar tiempo de desarrollo porque contienen numerosas funciones útiles ya escritas y listas para utilizar. La desventaja es que las API de Windows puede ser difíciles trabajar con e implacable cuando surgen problemas.  
  
 Las API de Windows representan una categoría especial de interoperabilidad. Las API de Windows no utilizan código administrado, no tiene integrado bibliotecas de tipos y utilizar tipos de datos que son diferentes a los que se usan con Visual Studio. Debido a estas diferencias, y como las API de Windows no son objetos COM, la interoperabilidad con las API de Windows y el [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] se realiza mediante la plataforma de invocación, o PInvoke. Invocación de plataforma es un servicio que habilita el código administrado llame a funciones no administradas implementadas en archivos DLL. Para obtener más información, consulte [consumir funciones de DLL no administradas](http://msdn.microsoft.com/library/eca7606e-ebfb-4f47-b8d9-289903fdc045). Puede utilizar PInvoke en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] utilizando la `Declare` instrucción o aplicar el `DllImport` de atributo a un procedimiento vacío.  
  
 Llamadas de API de Windows eran una parte importante de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] de programación en el pasado, pero rara vez son necesarias con [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]. Siempre que sea posible, debe utilizar código administrado desde el [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] para realizar tareas en lugar de llamadas a la API de Windows. Este tutorial proporciona información para aquellas situaciones en que las API de Windows es necesaria.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="api-calls-using-declare"></a>Llamadas a API utilizando Declare  
 Es la manera más común para llamar a las API de Windows mediante el `Declare` instrucción.  
  
#### <a name="to-declare-a-dll-procedure"></a>Para declarar un procedimiento DLL  
  
1.  Determinar el nombre de la función que desea llamar, además de sus argumentos, tipos de argumentos y devolver el valor, así como el nombre y la ubicación de la DLL que lo contiene.  
  
    > [!NOTE]
    >  Para obtener información completa sobre las API de Windows, consulte la documentación del SDK de Win32 en la API de Windows. Para obtener más información acerca de las constantes que utilizan las API de Windows, examine los archivos de encabezado, como Windows.h incluido con el SDK de la plataforma.  
  
2.  Abra un nuevo proyecto de aplicación de Windows, haga clic en **nueva** en el **archivo** menú y, a continuación, haga clic en **proyecto**. Aparecerá el cuadro de diálogo **Nuevo proyecto** .  
  
3.  Seleccione **aplicación Windows** en la lista de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] plantillas de proyecto. Se muestra el nuevo proyecto.  
  
4.  Agregue las siguientes `Declare` función a la clase o módulo en el que desea utilizar el archivo DLL:  
  
     [!code-vb[VbVbalrInterop&#9;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### <a name="parts-of-the-declare-statement"></a>Partes de la instrucción Declare  
 El `Declare` instrucción incluye los siguientes elementos.  
  
#### <a name="auto-modifier"></a>Modificador Auto  
 El `Auto` modificador indica el tiempo de ejecución para convertir la cadena en función del nombre de método según las reglas de common language runtime (o el nombre de alias si se especifica).  
  
#### <a name="lib-and-alias-keywords"></a>Palabras clave lib y Alias  
 El siguiente nombre el `Function` palabra clave es el nombre que el programa utiliza para tener acceso a la función importada. Puede ser el mismo que el nombre real de la función que llama, o puede utilizar cualquier nombre de procedimiento válido y, a continuación, emplear el `Alias` (palabra clave) para especificar el nombre real de la función que llama.  
  
 Especifique el `Lib` (palabra clave), seguido por el nombre y ubicación del archivo DLL que contiene la función que llama. No es necesario especificar la ruta de acceso para los archivos ubicados en los directorios de sistema de Windows.  
  
 Utilice la `Alias` palabra clave si el nombre de la función que llama no es válido [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] nombre del procedimiento o entra en conflicto con el nombre de otros elementos de la aplicación. `Alias`indica el nombre real de la función que se llama.  
  
#### <a name="argument-and-data-type-declarations"></a>Argumento y las declaraciones de tipo de datos  
 Declare los argumentos y sus tipos de datos. Esta parte puede resultar desafiante porque los tipos de datos que utiliza Windows no se corresponden con los tipos de datos de Visual Studio. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]realiza un gran parte del trabajo: convertir los argumentos en tipos de datos compatibles, un proceso denominado *el cálculo de referencias*. Se puede controlar explícitamente cómo se serializan los argumentos utilizando el <xref:System.Runtime.InteropServices.MarshalAsAttribute>atributo definido en el <xref:System.Runtime.InteropServices>espacio de nombres.</xref:System.Runtime.InteropServices> </xref:System.Runtime.InteropServices.MarshalAsAttribute>  
  
> [!NOTE]
>  Las versiones anteriores de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] permitían declarar parámetros `As Any`, lo que significa que los datos de los datos podría utilizarse tipo. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]requiere el uso de un tipo de datos específico para todas las `Declare` instrucciones.  
  
#### <a name="windows-api-constants"></a>Constantes de API de Windows  
 Algunos argumentos son combinaciones de constantes. Por ejemplo, el `MessageBox` API que se muestra en este tutorial acepta un argumento de entero denominado `Typ` que controla cómo se muestra el cuadro de mensaje. Puede determinar el valor numérico de estas constantes examinando el `#define` instrucciones en el archivo WinUser.h. Los valores numéricos se muestran generalmente en hexadecimal, por lo que puede utilizar una calculadora para sumarlos y convertirlos a decimal. Por ejemplo, si desea combinar las constantes del estilo de exclamación `MB_ICONEXCLAMATION` 0 x 00000030 y el valor Sí/No estilo `MB_YESNO` 0 x 00000004, puede sumar los números y obtener un resultado de 0 x 00000034, o 52 decimal. Aunque puede utilizar el resultado decimal directamente, es mejor declarar estos valores como constantes en la aplicación y combinarlos utilizando el `Or` operador.  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>Declarar constantes para las llamadas de API de Windows  
  
1.  Consulte la documentación de la función de Windows que está llamando. Determinar el nombre de las constantes que utiliza y el nombre del archivo .h que contiene los valores numéricos para estas constantes.  
  
2.  Utilice un editor de texto como Bloc de notas, para ver el contenido del archivo de encabezado (. h) y busque los valores asociados con las constantes que está utilizando. Por ejemplo, el `MessageBox` API utiliza la constante `MB_ICONQUESTION` para mostrar un signo de interrogación en el cuadro de mensaje. La definición de `MB_ICONQUESTION` está en WinUser.h y aparece como sigue:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  Agregar equivalente `Const` instrucciones a la clase o módulo para que estas constantes estén disponibles para su aplicación. Por ejemplo:  
  
     [!code-vb[VbVbalrInterop&#11;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### <a name="to-call-the-dll-procedure"></a>Para llamar al procedimiento DLL  
  
1.  Agregue un botón denominado `Button1` para el inicio del formulario para el proyecto y, a continuación, haga doble clic en él para ver su código. Se muestra el controlador de eventos para el botón.  
  
2.  Agregue código a la `Click` el controlador de eventos para el botón agregado para llamar al procedimiento y proporcione los argumentos correspondientes:  
  
     [!code-vb[VbVbalrInterop&#12;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  Ejecute el proyecto presionando F5. Aparece el cuadro de mensaje con ambos **Sí** y **n** botones de respuesta. Haga clic en cualquiera de ellos.  
  
#### <a name="data-marshaling"></a>Serialización de datos  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Convierte los tipos de datos de parámetros y valores devueltos para las llamadas API de Windows, pero se pueden utilizar automáticamente la `MarshalAs` atributo para especificar explícitamente los tipos de datos no administrados que espera una API. Para obtener más información acerca de la serialización de interoperabilidad, consulte [interoperativo](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a).  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>Para utilizar Declare y MarshalAs en una llamada API  
  
1.  Determinar el nombre de la función que desea llamar y sus argumentos, tipos de datos y valor devuelto.  
  
2.  Para simplificar el acceso a la `MarshalAs` atributo, agregue un `Imports` en la parte superior del código de la clase o módulo, como en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrInterop&#13;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  Agregue el prototipo de la función importada a la clase o módulo que está utilizando y aplique el `MarshalAs` a los parámetros de atributo o valor devuelto. En el ejemplo siguiente, una llamada a una API que espera el tipo `void*` se serializa como `AsAny`:  
  
     [!code-vb[VbVbalrInterop&#14;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## <a name="api-calls-using-dllimport"></a>Llamadas a API utilizando DllImport  
 El `DllImport` atributo proporciona una segunda forma de llamar a funciones de DLL sin bibliotecas de tipos. `DllImport`es prácticamente equivalente a una `Declare` instrucción pero proporciona más control sobre cómo se llama a funciones.  
  
 Puede usar `DllImport` con la mayoría de API de Windows llama siempre que la llamada hace referencia a un compartido (a veces denominado *estático*) (método). No puede utilizar métodos que requieren una instancia de una clase. A diferencia de `Declare` instrucciones, `DllImport` llamadas no se pueden utilizar el `MarshalAs` atributo.  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>Llamar a una API de Windows con el atributo DllImport  
  
1.  Abra un nuevo proyecto de aplicación de Windows, haga clic en **nueva** en el **archivo** menú y, a continuación, haga clic en **proyecto**. Aparecerá el cuadro de diálogo **Nuevo proyecto** .  
  
2.  Seleccione **aplicación Windows** en la lista de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] plantillas de proyecto. Se muestra el nuevo proyecto.  
  
3.  Agregue un botón denominado `Button2` al formulario de inicio.  
  
4.  Haga doble clic en `Button2` para abrir la vista de código del formulario.  
  
5.  Para simplificar el acceso a `DllImport`, agregue un `Imports` en la parte superior del código para la clase de formulario de inicio:  
  
     [!code-vb[VbVbalrInterop&#13;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  Declare una función vacía anterior la `End Class` instrucción para el formulario y el nombre de la función `MoveFile`.  
  
7.  Aplicar el `Public` y `Shared` modificadores a la declaración de función y los parámetros de conjunto `MoveFile` basándose en los argumentos que utiliza la función API de Windows:  
  
     [!code-vb[VbVbalrInterop Nº&16;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     La función puede tener cualquier nombre de procedimiento válido; el `DllImport` atributo especifica el nombre del archivo DLL. También controla el cálculo de referencias de interoperabilidad para los parámetros y valores devueltos, de modo que pueda elegir los tipos de datos de Visual Studio que son similares a los datos de tipos que utiliza la API.  
  
8.  Aplicar el `DllImport` de atributo a la función vacía. El primer parámetro es el nombre y la ubicación de la DLL que contiene la función que llama. No es necesario especificar la ruta de acceso para los archivos ubicados en los directorios de sistema de Windows. El segundo parámetro es un argumento con nombre que especifica el nombre de la función de la API de Windows. En este ejemplo, el `DllImport` atributo hace que las llamadas a `MoveFile` se reenvíen a `MoveFileW` en KERNEL32. DLL. El `MoveFileW` método copia un archivo de la ruta de acceso `src` a la ruta de acceso `dst`.  
  
     [!code-vb[VbVbalrInterop&#17;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. Agregue código a la `Button2_Click` el controlador de eventos para llamar a la función:  
  
     [!code-vb[VbVbalrInterop&#18;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. Cree un archivo llamado Test.txt y colóquelo en el directorio C:\Tmp del disco duro. Si es necesario, cree el directorio/Tmp.  
  
11. Presione F5 para iniciar la aplicación. Aparece el formulario principal.  
  
12. Haga clic en **Button2**. Si se puede mover el archivo, se muestra el mensaje "el archivo se movió correctamente".  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.DllImportAttribute></xref:System.Runtime.InteropServices.DllImportAttribute>   
 <xref:System.Runtime.InteropServices.MarshalAsAttribute></xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Automático](../../../visual-basic/language-reference/modifiers/auto.md)   
 [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)   
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Crear prototipos en código administrado](http://msdn.microsoft.com/library/ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d)   
 [Referencias de un delegado como un método de devolución de llamada](http://msdn.microsoft.com/library/6ddd7866-9804-4571-84de-83f5cc017a5a)
