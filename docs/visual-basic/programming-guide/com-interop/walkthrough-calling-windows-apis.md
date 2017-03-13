---
title: "Tutorial: Llamar a las API de Windows (Visual Basic) | Microsoft Docs"
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
  - "llamadas API, tutoriales [Visual Basic]"
  - "Declare (instrucción), declarar funciones de DLL"
  - "DllImport (atributo), llamar a API de Windows"
  - "DLL, llamar"
  - "invocación de plataforma, tutoriales"
  - "tutoriales [Visual Basic], llamadas API"
  - "API de Windows, llamar"
  - "API de Windows, tutoriales"
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Tutorial: Llamar a las API de Windows (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Las API de Windows son bibliotecas de vínculos dinámicos \(DLL\) que forman parte del sistema operativo Windows.  Se utilizan para realizar tareas cuando resulta difícil escribir procedimientos equivalentes.  Por ejemplo, Windows proporciona una función denominada `FlashWindowEx` que permite que la barra de título de una aplicación alterne entre un sombreado claro y otro oscuro.  
  
 La ventaja de utilizar las API de Windows en el código es que pueden ahorrar tiempo porque contienen numerosas funciones útiles ya escritas y listas para utilizar.  La desventaja es que puede resultar difícil trabajar con las API de Windows y pueden ser implacables cuando las cosas van mal.  
  
 Las API de Windows representan una categoría especial de interoperabilidad.  Las API de Windows no utilizan código administrado, no tienen bibliotecas de tipos integradas y utilizan tipos de datos que son diferentes a los que se utilizan en Visual Studio.  Debido a estas diferencias y a que las API de Windows no son objetos COM, la interoperabilidad con las API de Windows y [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] se lleva a cabo mediante la invocación de la plataforma o PInvoke.  Invocación de la plataforma es un servicio que permite al código administrado llamar a funciones no administradas implementadas en archivos DLL.  Para obtener más información, vea [Consuming Unmanaged DLL Functions](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md).  Puede utilizar PInvoke en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] mediante la instrucción `Declare` o aplicando el atributo `DllImport` a un procedimiento vacío.  
  
 Las llamadas API de Windows constituían en el pasado una parte importante de la programación de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], pero en [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] pocas veces resultan necesarias.  Siempre que sea posible, debe utilizar código administrado en [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] para llevar a cabo tareas en lugar de utilizar llamadas API de Windows.  Este tutorial proporciona información sobre aquellas situaciones en las que es necesario utilizar las API de Windows.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
## Llamadas API usando Declare  
 El modo más común de llamar a las API de Windows es utilizar la instrucción `Declare`.  
  
#### Para declarar un procedimiento de DLL  
  
1.  Determine el nombre de la función que desea llamar y sus argumentos, los tipos de argumento y el valor devuelto, así como el nombre y la ubicación de la DLL que la contiene.  
  
    > [!NOTE]
    >  Para obtener información completa sobre las API de Windows, consulte la documentación Win32 SDK relacionada con la API de Windows de Platform SDK.  Para obtener más información sobre las constantes que utilizan las API de Windows, vea los archivos de encabezado, como Windows.h, que se incluyen en el SDK de la plataforma.  
  
2.  En el menú **Archivo**, haga clic en **Nuevo** para abrir un nuevo proyecto de aplicación para Windows y, a continuación, haga clic en **Proyecto**.  Aparecerá el cuadro de diálogo **Nuevo proyecto**.  
  
3.  Seleccione **Aplicación Windows** en la lista de plantillas de proyecto de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Aparecerá el proyecto nuevo.  
  
4.  Agregue la función `Declare` siguiente a la clase o al módulo en el que desea utilizar el archivo DLL:  
  
     [!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### Partes de la instrucción Declare  
 La instrucción `Declare` incluye los siguientes elementos.  
  
#### Modificador Auto  
 El modificador `Auto` indica al motor en tiempo de ejecución que convierta la cadena basada en el nombre del método de acuerdo con las reglas de Common Language Runtime \(o el alias, si se ha especificado\).  
  
#### Palabras clave Lib y Alias  
 El nombre que sigue a la palabra clave `Function` es el nombre que utiliza el programa para tener acceso a la función importada.  Puede ser igual que el nombre real de la función a la que llama; o bien, puede utilizar cualquier nombre de procedimiento válido y utilizar después la palabra clave `Alias` para especificar el nombre real de la función a la que llama.  
  
 Especifique la palabra clave `Lib` seguida del nombre y la ubicación de la DLL que contiene la función a la que se está llamando.  No es necesario que especifique la ruta de acceso de los archivos ubicados en los directorios del sistema de Windows.  
  
 Utilice la palabra clave `Alias` si el nombre de la función a la que llama no es un nombre de procedimiento válido de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] o si está en conflicto con el nombre de otros elementos de la aplicación.  `Alias` indica el nombre real de la función a la que se llama.  
  
#### Declaraciones de argumentos y tipos de datos  
 Declare los argumentos y sus tipos de datos.  Esta parte puede suponer un reto porque los tipos de datos que Windows usa no corresponden a los tipos de datos de Visual Studio.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] se encarga de gran parte del trabajo ya que convierte los argumentos en tipos de datos compatibles; este proceso se denomina *cálculo de referencias*.  Puede controlar explícitamente el modo en que se calculan las referencias de los argumentos mediante el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> definido en el espacio de nombres <xref:System.Runtime.InteropServices>.  
  
> [!NOTE]
>  Las versiones anteriores de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] permitían declarar parámetros `As Any`, lo que significa que se podían utilizar datos de cualquier tipo.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] requiere que se utilice un tipo de datos específico en todas las instrucciones `Declare`.  
  
#### Constantes de las API de Windows  
 Algunos argumentos son combinaciones de constantes.  Por ejemplo, la API `MessageBox` que se muestra en este tutorial acepta un argumento Integer denominado `Typ` que controla cómo se muestra el cuadro de mensaje.  Puede determinar el valor numérico de estas constantes examinando las instrucciones `#define` en el archivo WinUser.h.  Los valores numéricos se muestran generalmente en hexadecimal, de modo que se puede utilizar una calculadora para agregarlos y convertirlos a decimal.  Por ejemplo, si desea combinar las constantes del estilo de exclamación `MB_ICONEXCLAMATION` 0x00000030 y el estilo sí\/no `MB_YESNO` 0x00000004, puede sumar los números y obtener el resultado de 0x00000034, o 52 en el sistema decimal.  Aunque puede utilizar el resultado decimal directamente, es mejor declarar estos valores como constantes en la aplicación y combinarlos utilizando el operador `Or`.  
  
###### Para declarar constantes para las llamadas API de Windows  
  
1.  Consulte la documentación de la función de Windows a la que está llamando.  Determine el nombre de las constantes que utiliza y el nombre del archivo .h que contiene los valores numéricos de estas constantes.  
  
2.  Utilice un editor de texto, como el Bloc de notas, para ver el contenido del archivo de encabezado .h y busque los valores asociados con las constantes que está utilizando.  Por ejemplo, la API `MessageBox` utiliza la constante `MB_ICONQUESTION` para mostrar un signo de interrogación en el cuadro de mensaje.  La definición para `MB_ICONQUESTION` está en WinUser.h y aparece como sigue:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  Agregue instrucciones `Const` equivalentes en la clase o el módulo para que estas constantes estén disponibles para la aplicación.  Por ejemplo:  
  
     [!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### Para llamar al procedimiento de DLL  
  
1.  Agregue un botón denominado `Button1` al formulario de inicio del proyecto y haga doble clic en él para ver su código.  Aparecerá el controlador de eventos del botón.  
  
2.  Agregue código al controlador de eventos `Click` del botón que ha agregado para llamar al procedimiento, y proporcione los argumentos correspondientes:  
  
     [!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  Presione F5 para ejecutar el proyecto.  El cuadro de mensaje aparecerá con dos botones de respuesta **Sí** y **No**.  Haga clic en alguno de ellos.  
  
#### Cálculo de referencias de datos  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] convierte automáticamente los tipos de datos de parámetros y valores devueltos para las llamadas API de Windows, aunque se puede utilizar el atributo `MarshalAs` para especificar de manera explícita los tipos de datos no administrados que espera una API.  Para obtener más información sobre el cálculo de referencias de interoperabilidad, vea [Interop Marshaling](../Topic/Interop%20Marshaling.md).  
  
###### Para utilizar Declare y MarshalAs en una llamada API  
  
1.  Determine el nombre de la función a la que desea llamar y sus argumentos, tipos de datos y valor devuelto.  
  
2.  Para simplificar el acceso al atributo `MarshalAs`, agregue una instrucción `Imports` en la parte superior del código de la clase o módulo, como en el siguiente ejemplo:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  Agregue el prototipo de la función importada en la clase o módulo que está utilizando y aplique el atributo `MarshalAs` a los parámetros o al valor devuelto.  En el siguiente ejemplo, se calculan las referencias de una llamada API que espera el tipo `void*` como `AsAny`:  
  
     [!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## Llamadas API con DllImport  
 El atributo `DllImport` proporciona una alternativa para llamar a las funciones de DLL sin bibliotecas de tipos.  El atributo `DllImport` es prácticamente equivalente a la instrucción `Declare` pero proporciona un mayor control sobre la forma en que se llama a las funciones.  
  
 Puede utilizar `DllImport` con la mayoría de las llamadas API de Windows siempre y cuando la llamada haga referencia a un método compartido \(a veces denominado *static*\).  No puede utilizar métodos que requieran una instancia de una clase.  A diferencia de las instrucciones `Declare`, las llamadas a `DllImport` no pueden utilizar el atributo `MarshalAs`.  
  
#### Para llamar a una API de Windows utilizando el atributo DllImport  
  
1.  En el menú **Archivo**, haga clic en **Nuevo** para abrir un nuevo proyecto de aplicación para Windows y, a continuación, haga clic en **Proyecto**.  Aparecerá el cuadro de diálogo **Nuevo proyecto**.  
  
2.  Seleccione **Aplicación Windows** en la lista de plantillas de proyecto de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Aparecerá el proyecto nuevo.  
  
3.  Agregue un botón denominado `Button2` al formulario de inicio.  
  
4.  Haga doble clic en `Button2` para abrir la vista de código del formulario.  
  
5.  Para simplificar el acceso a `DllImport`, agregue una instrucción `Imports` a la parte superior del código para la clase del formulario de inicio:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  Declare una función vacía que preceda a la instrucción `End Class` para el formulario y dé a la función el nombre `MoveFile`.  
  
7.  Aplique los modificadores `Public` y `Shared` a la declaración de la función y establezca parámetros para `MoveFile` de acuerdo con los argumentos que utiliza la función de la API de Windows:  
  
     [!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     La función puede tener cualquier nombre de procedimiento válido; el atributo `DllImport` especifica el nombre de la DLL.  También controla el cálculo de referencias de interoperabilidad de los parámetros y los valores devueltos, de manera que puede elegir tipos de datos de Visual Studio que sean similares a los tipos de datos que utiliza la API.  
  
8.  Aplique el atributo `DllImport` a la función vacía.  El primer parámetro es el nombre y la ubicación de la DLL que contiene la función a la que llama.  No es necesario que especifique la ruta de acceso de los archivos ubicados en los directorios del sistema de Windows.  El segundo parámetro es un argumento con nombre que especifica el nombre de la función de la API de Windows.  En este ejemplo, el atributo `DllImport` hace que las llamadas a `MoveFile` se reenvíen a `MoveFileW` en KERNEL32.DLL.  El método `MoveFileW` copia un archivo de la ruta de acceso `src` a la ruta de acceso `dst`.  
  
     [!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. Agregue el código al controlador de eventos `Button2_Click` para llamar a la función:  
  
     [!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. Cree un archivo con el nombre Test.txt y sitúelo en el directorio C:\\Tmp del disco duro.  Cree el directorio Tmp si es necesario.  
  
11. Presione F5 para iniciar la aplicación.  Aparecerá el formulario principal.  
  
12. Haga clic en **Button2**.  Aparecerá el mensaje "El archivo se ha movido correctamente" si se puede mover el archivo.  
  
## Vea también  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)   
 [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)   
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Creating Prototypes in Managed Code](../Topic/Creating%20Prototypes%20in%20Managed%20Code.md)   
 [Marshaling a Delegate as a Callback Method](../Topic/Marshaling%20a%20Delegate%20as%20a%20Callback%20Method.md)