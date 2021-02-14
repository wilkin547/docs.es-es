---
description: 'Más información sobre: Tutorial: llamar a las API de Windows (Visual Basic)'
title: 'Tutorial: Llamadas a las API de Windows'
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
ms.openlocfilehash: 9ffe89cabade780dbe1ced189a92c37e822c59e9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100427263"
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Tutorial: Llamar a las API de Windows (Visual Basic)

Las API de Windows son bibliotecas de vínculos dinámicos (dll) que forman parte del sistema operativo Windows. Se usan para realizar tareas cuando es difícil escribir procedimientos equivalentes propios. Por ejemplo, Windows proporciona una función denominada `FlashWindowEx` que le permite hacer que la barra de título de una aplicación alterne entre sombras claras y oscuras.  
  
 La ventaja de usar las API de Windows en el código es que pueden ahorrar tiempo de desarrollo porque contienen docenas de funciones útiles que ya están escritas y en espera de usarse. El inconveniente es que las API de Windows pueden ser difíciles de trabajar con y Unforgiving cuando hay algún problema.  
  
 Las API de Windows representan una categoría especial de interoperabilidad. Las API de Windows no usan código administrado, no tienen bibliotecas de tipos integrados y usan tipos de datos que son diferentes de los que se usan con Visual Studio. Debido a estas diferencias, y dado que las API de Windows no son objetos COM, la interoperabilidad con las API de Windows y el .NET Framework se realiza mediante la invocación de plataforma o PInvoke. La invocación de plataforma es un servicio que permite al código administrado llamar a funciones no administradas implementadas en archivos dll. Para obtener más información, vea [consumir funciones dll no administradas](../../../framework/interop/consuming-unmanaged-dll-functions.md). Puede usar PInvoke en Visual Basic mediante la `Declare` instrucción o aplicando el `DllImport` atributo a un procedimiento vacío.  
  
 Las llamadas a la API de Windows eran una parte importante de la programación de Visual Basic en el pasado, pero rara vez son necesarias con Visual Basic .NET. Siempre que sea posible, debe usar código administrado desde el .NET Framework para realizar tareas, en lugar de llamadas a la API de Windows. En este tutorial se proporciona información sobre las situaciones en las que es necesario usar las API de Windows.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a>Llamadas API mediante declare  

 La forma más común de llamar a las API de Windows es mediante la `Declare` instrucción.  
  
### <a name="to-declare-a-dll-procedure"></a>Para declarar un procedimiento DLL  
  
1. Determine el nombre de la función a la que desea llamar, además de sus argumentos, tipos de argumentos y valor devuelto, así como el nombre y la ubicación del archivo DLL que lo contiene.  
  
    > [!NOTE]
    > Para obtener información completa sobre las API de Windows, consulte la documentación del SDK de Win32 en la API de Windows de Platform SDK. Para obtener más información sobre las constantes que usan las API de Windows, examine los archivos de encabezado como Windows. h incluido con el SDK de la plataforma.  
  
2. Abra un nuevo proyecto de aplicación para Windows; para ello, haga clic en **nuevo** en el menú **archivo** y, a continuación, haga clic en **proyecto**. Aparecerá el cuadro de diálogo **Nuevo proyecto** .  
  
3. Seleccione **aplicación de Windows** en la lista de plantillas de proyecto de Visual Basic. Se muestra el nuevo proyecto.  
  
4. Agregue la siguiente `Declare` función a la clase o módulo en el que desea utilizar el archivo dll:  
  
     [!code-vb[VbVbalrInterop#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#9)]  
  
### <a name="parts-of-the-declare-statement"></a>Partes de la instrucción Declare  

 La `Declare` instrucción incluye los siguientes elementos.  
  
#### <a name="auto-modifier"></a>Auto (modificador)  

 El `Auto` modificador indica al tiempo de ejecución que convierta la cadena basándose en el nombre del método de acuerdo con las reglas de Common Language Runtime (o el nombre de alias si se especifica).  
  
#### <a name="lib-and-alias-keywords"></a>Palabras clave lib y alias  

 El nombre que sigue `Function` a la palabra clave es el nombre que usa el programa para tener acceso a la función importada. Puede ser el mismo nombre real de la función a la que se está llamando, o bien se puede usar cualquier nombre de procedimiento válido y, a continuación, utilizar la `Alias` palabra clave para especificar el nombre real de la función a la que se está llamando.  
  
 Especifique la `Lib` palabra clave, seguida del nombre y la ubicación del archivo DLL que contiene la función a la que llama. No es necesario especificar la ruta de acceso de los archivos que se encuentran en los directorios del sistema de Windows.  
  
 Use la `Alias` palabra clave si el nombre de la función a la que se está llamando no es un nombre de procedimiento Visual Basic válido o está en conflicto con el nombre de otros elementos de la aplicación. `Alias` indica el nombre real de la función que se va a llamar.  
  
#### <a name="argument-and-data-type-declarations"></a>Declaraciones de argumentos y tipos de datos  

 Declare los argumentos y sus tipos de datos. Esta parte puede ser desafiante, ya que los tipos de datos que usa Windows no se corresponden con los tipos de datos de Visual Studio. Visual Basic realiza una gran cantidad de trabajo mediante la conversión de argumentos en tipos de datos compatibles, un proceso denominado *serialización*. Puede controlar explícitamente cómo se calculan las referencias de los argumentos mediante el <xref:System.Runtime.InteropServices.MarshalAsAttribute> atributo definido en el <xref:System.Runtime.InteropServices> espacio de nombres.  
  
> [!NOTE]
> Las versiones anteriores de Visual Basic permitían declarar parámetros `As Any` , lo que significa que se pueden usar datos de cualquier tipo de datos. Visual Basic requiere que se use un tipo de datos específico para todas las `Declare` instrucciones.  
  
#### <a name="windows-api-constants"></a>Constantes de la API de Windows  

 Algunos argumentos son combinaciones de constantes. Por ejemplo, la `MessageBox` API mostrada en este tutorial acepta un argumento de entero denominado `Typ` que controla cómo se muestra el cuadro de mensaje. Puede determinar el valor numérico de estas constantes mediante el examen de las `#define` instrucciones del archivo WinUser. h. Los valores numéricos se suelen mostrar en formato hexadecimal, por lo que es posible que desee usar una calculadora para agregarlos y convertirlos a decimal. Por ejemplo, si desea combinar las constantes del estilo de exclamación `MB_ICONEXCLAMATION` 0x00000030 y el estilo yes/no `MB_YESNO` 0x00000004, puede Agregar los números y obtener un resultado de 0x00000034 o 52 decimal. Aunque puede usar el resultado decimal directamente, es mejor declarar estos valores como constantes en la aplicación y combinarlos mediante el `Or` operador.  
  
##### <a name="to-declare-constants-for-windows-api-calls"></a>Para declarar constantes para las llamadas a la API de Windows  
  
1. Consulte la documentación de la función de Windows a la que está llamando. Determine el nombre de las constantes que utiliza y el nombre del archivo. h que contiene los valores numéricos de estas constantes.  
  
2. Use un editor de texto, como el Bloc de notas, para ver el contenido del archivo de encabezado (. h) y buscar los valores asociados a las constantes que está usando. Por ejemplo, la `MessageBox` API usa la constante `MB_ICONQUESTION` para mostrar un signo de interrogación en el cuadro de mensaje. La definición de `MB_ICONQUESTION` está en WinUser. h y aparece de la siguiente manera:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3. Agregue instrucciones equivalentes `Const` a la clase o módulo para que estas constantes estén disponibles para la aplicación. Por ejemplo:  
  
     [!code-vb[VbVbalrInterop#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#11)]  
  
###### <a name="to-call-the-dll-procedure"></a>Para llamar al procedimiento DLL  
  
1. Agregue un botón denominado `Button1` al formulario de inicio para el proyecto y, a continuación, haga doble clic en él para ver su código. Se muestra el controlador de eventos para el botón.  
  
2. Agregue código al `Click` controlador de eventos para el botón que agregó, para llamar al procedimiento y proporcione los argumentos adecuados:  
  
     [!code-vb[VbVbalrInterop#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#12)]  
  
3. Ejecute el proyecto presionando F5. El cuadro de mensaje se muestra con los botones **sí** y **sin** respuesta. Haga clic en cualquiera de ellas.  
  
#### <a name="data-marshaling"></a>Serialización de datos  

 Visual Basic convierte automáticamente los tipos de datos de los parámetros y los valores devueltos para las llamadas a la API de Windows, pero puede usar el `MarshalAs` atributo para especificar explícitamente los tipos de datos no administrados que una API espera. Para obtener más información sobre el cálculo de referencias de interoperabilidad, vea [serialización de interoperabilidad](../../../framework/interop/interop-marshaling.md).  
  
##### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>Para usar declare y MarshalAs en una llamada API  
  
1. Determine el nombre de la función a la que desea llamar, además de sus argumentos, tipos de datos y valor devuelto.  
  
2. Para simplificar el acceso al `MarshalAs` atributo, agregue una `Imports` instrucción a la parte superior del código de la clase o módulo, como en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
3. Agregue un prototipo de función para la función importada a la clase o módulo que está usando y aplique el `MarshalAs` atributo a los parámetros o el valor devuelto. En el ejemplo siguiente, se calculan las referencias de una llamada API que espera que el tipo `void*` sea `AsAny` :  
  
     [!code-vb[VbVbalrInterop#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#14)]  
  
## <a name="api-calls-using-dllimport"></a>Llamadas API con DllImport  

 El `DllImport` atributo proporciona una segunda manera de llamar a funciones en archivos dll sin bibliotecas de tipos. `DllImport` es aproximadamente equivalente a utilizar una `Declare` instrucción pero proporciona más control sobre cómo se llama a las funciones.  
  
 Puede usar `DllImport` con la mayoría de las llamadas a la API de Windows siempre y cuando la llamada haga referencia a un método compartido (a veces denominado *static*). No se pueden usar métodos que requieran una instancia de una clase. A diferencia `Declare` de las instrucciones, `DllImport` las llamadas no pueden usar el `MarshalAs` atributo.  
  
### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>Para llamar a una API de Windows mediante el atributo DllImport  
  
1. Abra un nuevo proyecto de aplicación para Windows; para ello, haga clic en **nuevo** en el menú **archivo** y, a continuación, haga clic en **proyecto**. Aparecerá el cuadro de diálogo **Nuevo proyecto** .  
  
2. Seleccione **aplicación de Windows** en la lista de plantillas de proyecto de Visual Basic. Se muestra el nuevo proyecto.  
  
3. Agregue un botón denominado `Button2` al formulario de inicio.  
  
4. Haga doble clic `Button2` para abrir la vista de código del formulario.  
  
5. Para simplificar el acceso a `DllImport` , agregue una `Imports` instrucción a la parte superior del código para la clase de formulario de Inicio:  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
6. Declare una función vacía antes de la `End Class` instrucción del formulario y asigne un nombre a la función `MoveFile` .  
  
7. Aplique los `Public` `Shared` modificadores y a la declaración de función y establezca los parámetros para en `MoveFile` función de los argumentos que usa la función de la API de Windows:  
  
     [!code-vb[VbVbalrInterop#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#16)]  
  
     La función puede tener cualquier nombre de procedimiento válido; el `DllImport` atributo especifica el nombre del archivo dll. También controla el cálculo de referencias de interoperabilidad para los parámetros y los valores devueltos, por lo que puede elegir los tipos de datos de Visual Studio que son similares a los tipos de datos que usa la API.  
  
8. Aplique el `DllImport` atributo a la función vacía. El primer parámetro es el nombre y la ubicación del archivo DLL que contiene la función a la que se está llamando. No es necesario especificar la ruta de acceso de los archivos que se encuentran en los directorios del sistema de Windows. El segundo parámetro es un argumento con nombre que especifica el nombre de la función en la API de Windows. En este ejemplo, el `DllImport` atributo obliga a que `MoveFile` se reenvíen las llamadas a `MoveFileW` en KERNEL32.DLL. El `MoveFileW` método copia un archivo de la ruta de acceso `src` a la ruta de acceso `dst` .  
  
     [!code-vb[VbVbalrInterop#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#17)]  
  
9. Agregue código al `Button2_Click` controlador de eventos para llamar a la función:  
  
     [!code-vb[VbVbalrInterop#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#18)]  
  
10. Cree un archivo denominado Test.txt y colóquelo en el directorio C:\Tmp del disco duro. Cree el directorio tmp si es necesario.  
  
11. Presione F5 para iniciar la aplicación. Aparece el formulario principal.  
  
12. Haga clic en **BUTTON2**. Se muestra el mensaje "el archivo se ha despasado correctamente" si se puede cambiar el archivo.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Declare Statement](../../language-reference/statements/declare-statement.md)
- [Automático](../../language-reference/modifiers/auto.md)
- [Alias](../../language-reference/statements/alias-clause.md)
- [Interoperabilidad COM](index.md)
- [Crear prototipos en código administrado](../../../framework/interop/creating-prototypes-in-managed-code.md)
- [Calcular las referencias de un delegado como un método de devolución de llamada](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
