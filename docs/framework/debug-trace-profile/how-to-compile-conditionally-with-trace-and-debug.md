---
title: Filtrar para compilar con Trace y Debug de forma condicional
ms.date: 03/30/2017
helpviewer_keywords:
- trace compiler options
- trace statements
- compiling source code, trace statements
- tracing [.NET Framework], enabling or disabling
- tracing [.NET Framework], compiling conditionally
- TRACE directive
- conditional compilation, tracing code
ms.assetid: 56d051c3-012c-42c1-9a58-7270edc624aa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76e442536e4c863031072adfb4d8716ca7a19aff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158663"
---
# <a name="how-to-compile-conditionally-with-trace-and-debug"></a>Filtrar para compilar con Trace y Debug de forma condicional
Al depurar una aplicación durante el desarrollo, el seguimiento y la salida de depuración aparecen en la ventana Salida de Visual Studio. Pero para incluir características de seguimiento en una aplicación implementada, tendrá que compilar las aplicaciones instrumentadas con la directiva de compilador **TRACE** habilitada. Esto permite que el código de seguimiento se compile en la versión de lanzamiento de la aplicación. Si no habilita la directiva **TRACE**, se ignorará todo el código de seguimiento durante la compilación y no se incluirá en el código ejecutable que se va a implementar.  
  
 Los métodos de depuración y seguimiento tienen atributos condicionales asociados. Por ejemplo, si el atributo condicional para el seguimiento es **true**, todas las instrucciones de seguimiento se incluyen dentro de un ensamblado (un archivo .exe o .dll compilado); si el atributo condicional de **Trace** es **false**, no se incluyen las instrucciones de seguimiento.  
  
 Para una compilación puede tener activados ambos, uno o ninguno de los atributos condicionales **Trace** o **Debug**. Por lo tanto, hay cuatro tipos de compilación: **Depurar**, **seguimiento**, ambos o ninguno. Algunas compilaciones de versión para la implementación de producción pueden no contener ninguno; la mayoría de las compilaciones de depuración contienen ambos.  
  
 La configuración del compilador para la aplicación se puede configurar de varias maneras:  
  
-   Las páginas de propiedades  
  
-   La línea de comandos  
  
-   **#CONST** (para Visual Basic) y **#define** (para C#)  
  
### <a name="to-change-compile-settings-from-the-property-pages-dialog-box"></a>Para cambiar la configuración de compilación desde el cuadro de diálogo de páginas de propiedades  
  
1.  En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo del proyecto.  
  
2.  Seleccione **Propiedades** en el menú contextual.  
  
    -   En Visual Basic, haga clic en la pestaña **Compilar** en el panel izquierdo de la página de propiedades. Después, haga clic en el botón **Opciones de compilación avanzadas** para mostrar el cuadro de diálogo **Configuración de compilador avanzada**. Seleccione las casillas correspondientes a los valores de configuración del compilador que desee habilitar. Desactive las casillas de los valores de configuración que desee deshabilitar.  
  
    -   En C#, haga clic en la pestaña **Compilar** en el panel izquierdo de la página de propiedades y, después, active las casillas correspondientes a los valores de configuración del compilador que quiere habilitar. Desactive las casillas de los valores de configuración que desee deshabilitar.  
  
### <a name="to-compile-instrumented-code-using-the-command-line"></a>Para compilar código instrumentado desde la línea de comandos  
  
1.  Establezca un modificador de compilación condicional en la línea de comandos. El compilador incluirá código de seguimiento o depuración en el archivo ejecutable.  
  
     Por ejemplo, la siguiente instrucción del compilador especificada en la línea de comandos incluiría el código de seguimiento en un ejecutable compilado:  
  
     Visual Basic: **vbc-r:System.dll -d: TRACE = TRUE -d: DEBUG = FALSE MiAplicación.vb**  
  
     Para C#: **csc-r:System.dll -d: TRACE -d: DEBUG = FALSE MiAplicación.cs**  
  
    > [!TIP]
    >  Para compilar varios archivos de aplicación, deje un espacio en blanco entre los nombres de archivo, por ejemplo, **MyApplication1.vb MyApplication2.vb MyApplication3.vb** o **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.  
  
     El significado de las directivas de compilación condicional usadas en los ejemplos anteriores es el siguiente:  
  
    |Directiva|Significado|  
    |---------------|-------------|  
    |`vbc`|compilador de Visual Basic|  
    |`csc`|Compilador de C#|  
    |`-r:`|Hace referencia a un ensamblado externo (EXE o DLL)|  
    |`-d:`|Define un símbolo de compilación condicional|  
  
    > [!NOTE]
    >  TRACE o DEBUG deben escribirse en letras mayúsculas. Para obtener más información sobre los comandos de compilación condicional, escriba `vbc /?` (para Visual Basic) o `csc /?` (para C#) en el símbolo del sistema. Para más información, vea [Building from the Command Line](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) (Compilar desde la línea de comandos) (C#) o [Invoking the Command-Line Compiler](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) (Invocar el compilador de línea de comandos) (Visual Basic).  
  
### <a name="to-perform-conditional-compilation-using-const-or-define"></a>Para realizar compilación condicional mediante #CONST o #define  
  
1.  Escriba la instrucción apropiada para su lenguaje de programación en la parte superior del archivo de código fuente.  
  
    |Lenguaje|Instrucción|Resultado|  
    |--------------|---------------|------------|  
    |**Visual Basic**|**#CONST TRACE = true**|Habilita el seguimiento|  
    ||**#CONST TRACE = false**|Deshabilita el seguimiento|  
    ||**#CONST DEBUG = true**|Habilita la depuración|  
    ||**#CONST DEBUG = false**|Deshabilita la depuración|  
    |**C#**|**#define TRACE**|Habilita el seguimiento|  
    ||**#undef TRACE**|Deshabilita el seguimiento|  
    ||**#define DEBUG**|Habilita la depuración|  
    ||**#undef DEBUG**|Deshabilita la depuración|  
  
### <a name="to-disable-tracing-or-debugging"></a>Para deshabilitar el seguimiento o la depuración  
  
Elimine la directiva de compilador del código fuente.  
  
\- o -  
  
Convierta en comentario la directiva de compilador.  
  
> [!NOTE]
>  Cuando esté preparado para compilar, puede elegir **Compilar** en el menú **Compilar**, o bien usar el método de línea de comandos, pero sin escribir **d:** para definir símbolos de compilación condicional.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento e instrumentación de aplicaciones](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
- [Filtrar para crear, inicializar y configurar modificadores de seguimiento](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)
- [Modificadores de seguimiento](../../../docs/framework/debug-trace-profile/trace-switches.md)
- [Agentes de escucha de seguimiento](../../../docs/framework/debug-trace-profile/trace-listeners.md)
- [Filtrar para agregar instrucciones de seguimiento al código de una aplicación](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)
- [Filtrar Establecer variables de entorno para la línea de comandos de Visual Studio](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)
- [Filtrar Invocar el compilador de línea de comandos](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)
