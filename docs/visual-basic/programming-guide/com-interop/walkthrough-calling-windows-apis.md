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
ms.openlocfilehash: 8fd63c2abedcd416937e2c281486bdc1716a275f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332331"
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Tutorial: Llamar a las API de Windows (Visual Basic)
API de Windows son bibliotecas de vínculos dinámicos (DLL) que forman parte del sistema operativo Windows. Usarlos para realizar tareas cuando resulta difícil escribir procedimientos equivalentes. Por ejemplo, Windows proporcionan una función denominada `FlashWindowEx` que permite que la barra de título de una aplicación alterne entre claro y oscuro.  
  
 La ventaja de usar las API de Windows en el código es que pueden ahorrar tiempo de desarrollo porque contienen docenas de funciones útiles que ya se han escrito y espera que se usará. La desventaja es que las API de Windows puede ser difíciles trabajar con e implacable cuando algo va mal.  
  
 Las API de Windows representan una categoría especial de interoperabilidad. Las API de Windows no utilizan código administrado, no tienen integradas las bibliotecas de tipos y utilizar tipos de datos que sean diferentes a los que se usan con Visual Studio. Debido a estas diferencias, y dado que las API de Windows no son objetos COM, la interoperabilidad con las API de Windows y el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] se realiza mediante la plataforma de invocación, o PInvoke. Invocación de plataforma es un servicio que permite código para llamar a funciones no administradas implementadas en archivos DLL administrado. Para obtener más información, consulte [consumir funciones de DLL no administradas](../../../framework/interop/consuming-unmanaged-dll-functions.md). Puede utilizar PInvoke en Visual Basic mediante el uso del `Declare` instrucción o aplicar el `DllImport` atributo a un procedimiento vacío.  
  
 Las llamadas de API de Windows eran una parte importante de Visual Basic de programación en el pasado, pero rara vez son necesarias con Visual Basic. NET. Siempre que sea posible, debe usar código administrado desde el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] para realizar tareas, en lugar de llamadas de API de Windows. En este tutorial se proporciona información para aquellas situaciones en las que el uso las API de Windows es necesaria.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a>Declaran mediante llamadas a API  
 Es la manera más común para llamar a API de Windows mediante el `Declare` instrucción.  
  
#### <a name="to-declare-a-dll-procedure"></a>Para declarar un procedimiento DLL  
  
1. Determinar el nombre de la función que desea llamar, además de sus argumentos, los tipos de argumento y devuelve el valor, así como el nombre y la ubicación del archivo DLL que lo contiene.  
  
    > [!NOTE]
    >  Para obtener información completa acerca de las API de Windows, consulte la documentación del SDK de Win32 en la API de Windows Platform SDK. Para obtener más información acerca de las constantes que utilizan las API de Windows, examine los archivos de encabezado como Windows.h incluido con el SDK de plataforma.  
  
2. Abra un nuevo proyecto de aplicación de Windows, haga clic en **New** en el **archivo** menú y, a continuación, haga clic en **proyecto**. Aparecerá el cuadro de diálogo **Nuevo proyecto** .  
  
3. Seleccione **aplicación Windows** en la lista de plantillas de proyecto de Visual Basic. Se muestra el nuevo proyecto.  
  
4. Agregue las siguientes `Declare` función a la clase o módulo en el que desea utilizar el archivo DLL:  
  
     [!code-vb[VbVbalrInterop#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#9)]  
  
### <a name="parts-of-the-declare-statement"></a>Partes de la instrucción Declare  
 El `Declare` instrucción incluye los siguientes elementos.  
  
#### <a name="auto-modifier"></a>Modificador Auto  
 El `Auto` modificador indica el tiempo de ejecución para convertir la cadena basándose en el nombre del método según las reglas de common language runtime (o nombre de alias si se especifica).  
  
#### <a name="lib-and-alias-keywords"></a>Palabras clave lib y Alias  
 El siguiente nombre el `Function` palabra clave es el nombre de su programa utiliza para tener acceso a la función importada. Puede ser el mismo que el nombre real de la función que llama, o puede usar cualquier nombre válido de procedimiento y, a continuación, emplean el `Alias` palabra clave para especificar el nombre real de la función que llama.  
  
 Especifique el `Lib` palabra clave, seguido por el nombre y ubicación del archivo DLL que contiene la función que llama. No es necesario especificar la ruta de acceso para los archivos ubicados en los directorios de sistema de Windows.  
  
 Use el `Alias` palabra clave si el nombre de la función que llama no es un nombre de procedimiento de Visual Basic válido o está en conflicto con el nombre de otros elementos de la aplicación. `Alias` indica el nombre real de la función que se llama.  
  
#### <a name="argument-and-data-type-declarations"></a>Argumento y declaraciones de tipos de datos  
 Declare los argumentos y sus tipos de datos. Esta parte puede resultar complicado porque los tipos de datos que usa Windows no corresponden a tipos de datos de Visual Studio. Visual Basic realiza un gran parte del trabajo mediante la conversión de argumentos a tipos de datos compatibles, un proceso denominado *serialización*. Puede controlar explícitamente cómo se serializan los argumentos mediante el uso de la <xref:System.Runtime.InteropServices.MarshalAsAttribute> atributo definido en el <xref:System.Runtime.InteropServices> espacio de nombres.  
  
> [!NOTE]
>  Las versiones anteriores de Visual Basic permitían declarar parámetros `As Any`, lo que significa que los datos de todos los datos se pueda usar tipo. Visual Basic requiere el uso de un tipo de datos específica para todos los `Declare` instrucciones.  
  
#### <a name="windows-api-constants"></a>Constantes de la API de Windows  
 Algunos argumentos son combinaciones de constantes. Por ejemplo, el `MessageBox` API que se muestra en este tutorial acepta un argumento de entero denominado `Typ` que controla cómo se muestra el cuadro de mensaje. Puede determinar el valor numérico de estas constantes examinando el `#define` instrucciones en el archivo WinUser.h. Los valores numéricos se muestran generalmente en formato hexadecimal, por lo que puede usar una calculadora para agregarlos y convertir en decimal. Por ejemplo, si desea combinar las constantes para el estilo de signo de exclamación `MB_ICONEXCLAMATION` 0 x 00000030 y el valor Sí/ningún estilo `MB_YESNO` 0 x 00000004, puede agregar los números y obtener un resultado de 0 x 00000034, o 52 decimal. Aunque puede utilizar el resultado decimal directamente, es mejor declarar estos valores como constantes en la aplicación y combinarlos con los `Or` operador.  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>Para declarar constantes para las llamadas de API de Windows  
  
1. Consulte la documentación de la función de Windows que está llamando. Determinar el nombre de las constantes que utiliza y el nombre del archivo .h que contiene los valores numéricos para estas constantes.  
  
2. Utilice un editor de texto como Bloc de notas, para ver el contenido del archivo de encabezado (. h) y busque los valores asociados con las constantes que usa. Por ejemplo, el `MessageBox` API usa la constante `MB_ICONQUESTION` para mostrar un signo de interrogación en el cuadro de mensaje. La definición de `MB_ICONQUESTION` está en WinUser.h y aparece como sigue:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3. Agregar equivalente `Const` instrucciones a su clase o módulo para que estas constantes estén disponibles para su aplicación. Por ejemplo:  
  
     [!code-vb[VbVbalrInterop#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#11)]  
  
###### <a name="to-call-the-dll-procedure"></a>Para llamar al procedimiento DLL  
  
1. Agregue un botón denominado `Button1` para el inicio de formulario para el proyecto y, a continuación, haga doble clic en él para ver su código. Se muestra el controlador de eventos para el botón.  
  
2. Agregue código a la `Click` controlador de eventos para el botón que agregó para llamar al procedimiento y proporcione los argumentos correspondientes:  
  
     [!code-vb[VbVbalrInterop#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#12)]  
  
3. Ejecute el proyecto presionando F5. Aparecerá el cuadro de mensaje con ambos **Sí** y **n** botones de respuesta. Haga clic en cualquiera de ellos.  
  
#### <a name="data-marshaling"></a>Serialización de datos  
 Visual Basic convierte automáticamente los tipos de datos de parámetros y valores devueltos para las llamadas API de Windows, pero puede usar el `MarshalAs` atributo para especificar explícitamente los tipos de datos no administrados que espera una API. Para obtener más información sobre la serialización de interoperabilidad, consulte [interoperativo](../../../framework/interop/interop-marshaling.md).  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>Para utilizar Declare y MarshalAs en una llamada API  
  
1. Determinar el nombre de la función que desea llamar, además de los argumentos, los tipos de datos, y el valor devuelto.  
  
2. Para simplificar el acceso a la `MarshalAs` atributo, agregue un `Imports` instrucción a la parte superior del código de la clase o módulo, como en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
3. Agregue un prototipo de función para la función importada a la clase o módulo que está usando y aplica el `MarshalAs` a los parámetros de atributo o valor devuelto. En el ejemplo siguiente, una llamada API que espera el tipo `void*` se serializa como `AsAny`:  
  
     [!code-vb[VbVbalrInterop#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#14)]  
  
## <a name="api-calls-using-dllimport"></a>Llamadas a API con DllImport  
 El `DllImport` atributo proporciona una segunda forma de llamar a funciones en archivos DLL sin bibliotecas de tipos. `DllImport` es aproximadamente equivalente a usar un `Declare` instrucción pero proporciona más control sobre cómo se llama a funciones.  
  
 Puede usar `DllImport` con la mayoría de API de Windows llama siempre que la llamada hace referencia a un compartido (a veces denominado *estático*) método. No se puede usar los métodos que requieren una instancia de una clase. A diferencia de `Declare` instrucciones, `DllImport` llamadas no se pueden usar el `MarshalAs` atributo.  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>Para llamar a una API de Windows mediante el atributo DllImport  
  
1. Abra un nuevo proyecto de aplicación de Windows, haga clic en **New** en el **archivo** menú y, a continuación, haga clic en **proyecto**. Aparecerá el cuadro de diálogo **Nuevo proyecto** .  
  
2. Seleccione **aplicación Windows** en la lista de plantillas de proyecto de Visual Basic. Se muestra el nuevo proyecto.  
  
3. Agregue un botón denominado `Button2` al formulario de inicio.  
  
4. Haga doble clic en `Button2` para abrir la vista de código del formulario.  
  
5. Para simplificar el acceso a `DllImport`, agregue un `Imports` instrucción a la parte superior del código de la clase de formulario de inicio:  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
6. Declare una función vacía anterior el `End Class` instrucción para el formulario y el nombre de la función `MoveFile`.  
  
7. Aplicar el `Public` y `Shared` los modificadores de la declaración de función y establecer parámetros para `MoveFile` según los argumentos que se usa la función de la API de Windows:  
  
     [!code-vb[VbVbalrInterop#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#16)]  
  
     La función puede tener cualquier nombre válido de procedimiento; el `DllImport` atributo especifica el nombre del archivo DLL. También controla la serialización de interoperabilidad para los parámetros y valores devueltos, para que pueda elegir los tipos de datos de Visual Studio que son similares a los datos de tipos que utiliza la API.  
  
8. Aplicar el `DllImport` atributo a la función vacía. El primer parámetro es el nombre y ubicación del archivo DLL que contiene la función que llama. No es necesario especificar la ruta de acceso para los archivos ubicados en los directorios de sistema de Windows. El segundo parámetro es un argumento con nombre que especifica el nombre de la función de la API de Windows. En este ejemplo, el `DllImport` atributo obliga a que las llamadas a `MoveFile` se reenvíen a `MoveFileW` en KERNEL32. ARCHIVO DLL. El `MoveFileW` método copia un archivo de la ruta de acceso `src` a la ruta de acceso `dst`.  
  
     [!code-vb[VbVbalrInterop#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#17)]  
  
9. Agregue código a la `Button2_Click` controlador de eventos para llamar a la función:  
  
     [!code-vb[VbVbalrInterop#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#18)]  
  
10. Cree un archivo llamado Test.txt y lo coloca en el directorio C:\Tmp del disco duro. Si es necesario, cree el directorio Tmp.  
  
11. Presione F5 para iniciar la aplicación. Aparece el formulario principal.  
  
12. Haga clic en **Button2**. Si se puede mover el archivo, se muestra el mensaje "el archivo se ha movido correctamente".  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Automático](../../../visual-basic/language-reference/modifiers/auto.md)
- [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)
- [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)
- [Crear prototipos en código administrado](../../../framework/interop/creating-prototypes-in-managed-code.md)
- [Calcular las referencias de un delegado como un método de devolución de llamada](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
