---
title: 'Tutorial: Llamar a las API de Windows (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls [Visual Basic], walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement [Visual Basic], declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
ms.openlocfilehash: bb98d842bfe65bdf637a789fc9a8319a70cb2bc8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644360"
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Tutorial: Llamar a las API de Windows (Visual Basic)
Las API de Windows son bibliotecas de vínculos dinámicos (DLL) que forman parte del sistema operativo Windows. Usarlos para realizar tareas cuando resulta difícil de escribir sus propios procedimientos equivalentes. Por ejemplo, Windows proporciona una función denominada `FlashWindowEx` que permite que la barra de título de una aplicación alterne entre claro y oscuro.  
  
 La ventaja de usar las API de Windows en el código es que pueden ahorrar tiempo de desarrollo porque contienen docenas de funciones útiles que ya se han escrito y en espera que se usará. La desventaja es que las API de Windows puede ser difíciles trabajar con e implacable si surgen problemas.  
  
 Las API de Windows representan una categoría especial de interoperabilidad. Las API de Windows no utilizan código administrado, no tienen integradas las bibliotecas de tipos y utilizar tipos de datos que son diferentes a los que se usan con Visual Studio. Debido a estas diferencias, y dado que las API de Windows no son objetos COM, la interoperabilidad con las API de Windows y la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] se lleva a cabo con la plataforma de invocación, o PInvoke. Invocación de plataforma es un servicio que habilita el código administrado llame a funciones no administradas implementadas en archivos DLL. Para obtener más información, consulte [consumir funciones DLL no administradas](../../../framework/interop/consuming-unmanaged-dll-functions.md). Puede utilizar PInvoke en Visual Basic utilizando la `Declare` instrucción o aplicar el `DllImport` atributo a un procedimiento vacío.  
  
 Llamadas API de Windows eran una parte importante de Visual Basic de programación en el pasado, pero rara vez son necesarias con Visual Basic. NET. Siempre que sea posible, debe utilizar código administrado desde el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] para realizar las tareas, en lugar de llamadas a la API de Windows. En este tutorial se proporciona información para aquellas situaciones en las que usar las API de Windows es necesaria.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a>Llamadas a API utilizando Declare  
 Es la manera más común para llamar a las API de Windows mediante el `Declare` instrucción.  
  
#### <a name="to-declare-a-dll-procedure"></a>Para declarar un procedimiento DLL  
  
1.  Determinar el nombre de la función que desea llamar, además de sus argumentos, los tipos de argumentos y devolver el valor, así como el nombre y la ubicación del archivo DLL que lo contiene.  
  
    > [!NOTE]
    >  Para obtener información completa acerca de las API de Windows, consulte la documentación del SDK de Win32 en la API de Windows de Platform SDK. Para obtener más información acerca de las constantes que utilizan las API de Windows, examine los archivos de encabezado, como Windows.h incluido con el SDK de plataforma.  
  
2.  Abra un nuevo proyecto de aplicación de Windows, haga clic en **New** en el **archivo** menú y, a continuación, haga clic en **proyecto**. Aparecerá el cuadro de diálogo **Nuevo proyecto** .  
  
3.  Seleccione **aplicación de Windows** en la lista de plantillas de proyecto de Visual Basic. Se muestra el nuevo proyecto.  
  
4.  Agregue las siguientes `Declare` función a la clase o módulo en el que desea utilizar el archivo DLL:  
  
     [!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### <a name="parts-of-the-declare-statement"></a>Partes de la instrucción Declare  
 El `Declare` instrucción incluye los siguientes elementos.  
  
#### <a name="auto-modifier"></a>Modificador Auto  
 El `Auto` modificador indica el tiempo de ejecución para convertir la cadena basándose en el nombre del método según reglas common language runtime (o nombre de alias si se especifica).  
  
#### <a name="lib-and-alias-keywords"></a>Palabras clave lib y Alias  
 El siguiente nombre el `Function` palabra clave es el nombre que el programa se usa para tener acceso a la función importada. Puede ser el mismo que el nombre real de la función que está llamando, o puede usar cualquier nombre válido de procedimiento y, a continuación, emplean el `Alias` palabra clave para especificar el nombre real de la función que está llamando.  
  
 Especifique el `Lib` (palabra clave), seguido por el nombre y la ubicación del archivo DLL que contiene la función que está llamando. No es necesario especificar la ruta de acceso para archivos que se encuentran en los directorios de sistema de Windows.  
  
 Use la `Alias` palabra clave si el nombre de la función de llamada no es un nombre de procedimiento de Visual Basic válido o está en conflicto con el nombre de otros elementos de la aplicación. `Alias` indica el nombre real de la función que se va a invocar.  
  
#### <a name="argument-and-data-type-declarations"></a>Argumento y declaraciones de tipos de datos  
 Declare los argumentos y sus tipos de datos. Esta parte puede ser un reto porque los tipos de datos que utiliza Windows no se corresponden con los tipos de datos de Visual Studio. Visual Basic realiza mucho del trabajo mediante la conversión de argumentos a los tipos de datos compatibles, un proceso denominado *serialización*. Puede controlar explícitamente cómo se serializan los argumentos mediante el uso de la <xref:System.Runtime.InteropServices.MarshalAsAttribute> atributo definido en el <xref:System.Runtime.InteropServices> espacio de nombres.  
  
> [!NOTE]
>  Las versiones anteriores de Visual Basic permitían declarar parámetros `As Any`, lo que significa que los datos de todos los datos se utilizará el tipo. Visual Basic requiere que utilice un tipo de datos específico para todas las `Declare` instrucciones.  
  
#### <a name="windows-api-constants"></a>Constantes de API de Windows  
 Algunos argumentos son combinaciones de constantes. Por ejemplo, el `MessageBox` API que se muestra en este tutorial acepta un argumento de entero denominado `Typ` que controla cómo se muestra el cuadro de mensaje. Puede determinar el valor numérico de estas constantes examinando la `#define` las instrucciones en el archivo WinUser.h. Los valores numéricos se muestran generalmente en hexadecimal, por lo que puede usar una calculadora para sumarlos y convertirlos en decimal. Por ejemplo, si desea combinar las constantes del estilo de exclamación `MB_ICONEXCLAMATION` 0 x 00000030 y el valor Sí/No estilo `MB_YESNO` 0 x 00000004, puede sumar los números y obtener un resultado de 0 x 00000034, o 52 decimal. Aunque puede utilizar el resultado decimal directamente, es mejor declarar estos valores como constantes en la aplicación y combinarlos utilizando el `Or` operador.  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>Declarar constantes para las llamadas de API de Windows  
  
1.  Consulte la documentación de la función de Windows que está llamando. Determinar el nombre de las constantes que utiliza y el nombre del archivo .h que contiene los valores numéricos para estas constantes.  
  
2.  Utilice un editor de texto, como el Bloc de notas para ver el contenido del archivo de encabezado (. h) y busque los valores asociados con las constantes que está utilizando. Por ejemplo, el `MessageBox` API utiliza la constante `MB_ICONQUESTION` para mostrar un signo de interrogación en el cuadro de mensaje. La definición de `MB_ICONQUESTION` está en WinUser.h y aparece como sigue:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  Agregar equivalente `Const` instrucciones a la clase o módulo para que estas constantes estén disponibles para la aplicación. Por ejemplo:  
  
     [!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### <a name="to-call-the-dll-procedure"></a>Para llamar al procedimiento DLL  
  
1.  Agregue un botón denominado `Button1` para el inicio del formulario para el proyecto y, a continuación, haga doble clic en él para ver su código. Se muestra el controlador de eventos para el botón.  
  
2.  Agregue código a la `Click` controlador de eventos para el botón que agregó, para llamar al procedimiento y proporcione los argumentos correspondientes:  
  
     [!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  Ejecute el proyecto presionando F5. Se muestra el cuadro de mensaje con ambos **Sí** y **n** botones de respuesta. Haga clic en uno.  
  
#### <a name="data-marshaling"></a>Serialización de datos  
 Visual Basic convierte automáticamente los tipos de datos de parámetros y valores devueltos para las llamadas API de Windows, pero puede usar el `MarshalAs` atributo para especificar explícitamente los tipos de datos no administrados que espera una API. Para obtener más información acerca de la serialización de interoperabilidad, consulte [cálculo de referencias interoperativo](../../../framework/interop/interop-marshaling.md).  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>Para utilizar Declare y MarshalAs en una llamada de API  
  
1.  Determinar el nombre de la función que desea llamar y sus argumentos, tipos de datos, y valor devuelto.  
  
2.  Para simplificar el acceso a la `MarshalAs` atributo, agregue un `Imports` instrucción al principio del código de la clase o módulo, como en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  Agregar un prototipo de función para la función importada a la clase o módulo que está usando y aplica el `MarshalAs` a los parámetros de atributo o valor devuelto. En el ejemplo siguiente, una llamada de API que espera el tipo `void*` se serializa como `AsAny`:  
  
     [!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## <a name="api-calls-using-dllimport"></a>Llamadas a API utilizando DllImport  
 El `DllImport` atributo proporciona una segunda forma de llamar a funciones en archivos DLL sin bibliotecas de tipos. `DllImport` es aproximadamente equivalente al usar un `Declare` instrucción pero proporciona más control sobre cómo se llama a funciones.  
  
 Puede usar `DllImport` con la mayoría de API de Windows llama siempre que la llamada hace referencia a un compartido (a veces denominado *estático*) método. No puede utilizar métodos que requieren una instancia de una clase. A diferencia de `Declare` instrucciones, `DllImport` llamadas no se pueden usar el `MarshalAs` atributo.  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>Para llamar a una API de Windows con el atributo DllImport  
  
1.  Abra un nuevo proyecto de aplicación de Windows, haga clic en **New** en el **archivo** menú y, a continuación, haga clic en **proyecto**. Aparecerá el cuadro de diálogo **Nuevo proyecto** .  
  
2.  Seleccione **aplicación de Windows** en la lista de plantillas de proyecto de Visual Basic. Se muestra el nuevo proyecto.  
  
3.  Agregue un botón denominado `Button2` al formulario de inicio.  
  
4.  Haga doble clic en `Button2` para abrir la vista de código del formulario.  
  
5.  Para simplificar el acceso a `DllImport`, agregue un `Imports` instrucción al principio del código de la clase de formulario de inicio:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  Declare una función vacía anterior la `End Class` instrucción para el formulario y el nombre de la función `MoveFile`.  
  
7.  Aplicar el `Public` y `Shared` modificadores a la declaración de función y los parámetros de conjunto `MoveFile` en función de los argumentos que utiliza la función API de Windows:  
  
     [!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     La función puede tener cualquier nombre de procedimiento válido; el `DllImport` atributo especifica el nombre del archivo DLL. También controla el cálculo de referencias de interoperabilidad para los parámetros y valores devueltos, para que pueda elegir los tipos de datos de Visual Studio que sean similares a los datos de tipos que utiliza la API.  
  
8.  Aplicar el `DllImport` de atributo a la función vacía. El primer parámetro es el nombre y la ubicación del archivo DLL que contiene la función que está llamando. No es necesario especificar la ruta de acceso para archivos que se encuentran en los directorios de sistema de Windows. El segundo parámetro es un argumento con nombre que especifica el nombre de la función en la API de Windows. En este ejemplo, el `DllImport` atributo hace que las llamadas a `MoveFile` se reenvíen a `MoveFileW` en KERNEL32. DLL. El `MoveFileW` método copia un archivo de la ruta de acceso `src` a la ruta de acceso `dst`.  
  
     [!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. Agregue código a la `Button2_Click` controlador de eventos para llamar a la función:  
  
     [!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. Crea un archivo llamado Test.txt y lo coloca en el directorio C:\Tmp en el disco duro. Cree el directorio Tmp si es necesario.  
  
11. Presione F5 para iniciar la aplicación. Aparece el formulario principal.  
  
12. Haga clic en **Button2**. Si se puede mover el archivo, se muestra el mensaje "el archivo se ha movido correctamente".  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)  
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Crear prototipos en código administrado](../../../framework/interop/creating-prototypes-in-managed-code.md)  
 [Serialización de un delegado como un método de devolución de llamada](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
