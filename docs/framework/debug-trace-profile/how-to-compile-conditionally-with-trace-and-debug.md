---
title: "How to: Compile Conditionally with Trace and Debug | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "trace compiler options"
  - "trace statements"
  - "compiling source code, trace statements"
  - "tracing [.NET Framework], enabling or disabling"
  - "tracing [.NET Framework], compiling conditionally"
  - "TRACE directive"
  - "conditional compilation, tracing code"
ms.assetid: 56d051c3-012c-42c1-9a58-7270edc624aa
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Compile Conditionally with Trace and Debug
Al depurar una aplicación durante el desarrollo, el seguimiento y la salida de depuración aparecen en la ventana Salida de Visual Studio.  No obstante, para incluir características de seguimiento en una aplicación implementada, hay que compilar las aplicaciones instrumentadas con la directiva de compilador **TRACE** habilitada.  Esto permite que el código de seguimiento se compile en la versión de lanzamiento de la aplicación.  Si no habilita la directiva **TRACE**, se ignorará todo el código de seguimiento durante la compilación y no se incluirá en el código ejecutable que se va a implementar.  
  
 Los métodos de depuración y seguimiento tienen atributos condicionales asociados.  Por ejemplo, si el atributo condicional para el seguimiento es **true**, todas las instrucciones de seguimiento se incluyen dentro de un ensamblado \(un archivo compilado .exe o .dll\); si el atributo condicional de **Trace** es **false**, no se incluyen las instrucciones de seguimiento.  
  
 Para una compilación puede tener activados ambos, uno o ninguno de los atributos condicionales **Trace** o **Debug**.  Por lo tanto, hay cuatro tipos de compilación: **Debug**, **Trace**, ambos o ninguno.  Algunas compilaciones de versión para la implementación de producción pueden no contener ninguno; la mayoría de las compilaciones de depuración contienen ambos.  
  
 La configuración del compilador para la aplicación se puede configurar de varias maneras:  
  
-   Las páginas de propiedades  
  
-   La línea de comandos  
  
-   **\#CONST** \(para Visual Basic\) y **\#define** \(para C\#\)  
  
### Para cambiar la configuración de compilación desde el cuadro de diálogo de páginas de propiedades  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el nodo del proyecto.  
  
2.  Elija **Propiedades** en menú contextual.  
  
    -   En Visual Basic, haga clic en la pestaña **Compilar** que está situada en el panel izquierdo de la página de propiedades. A continuación, haga clic en el botón **Opciones de compilación avanzadas** para mostrar el cuadro de diálogo **Configuración de compilador avanzada**.  Seleccione las casillas correspondientes a los valores de configuración del compilador que desee habilitar.  Desactive las casillas de los valores de configuración que desee deshabilitar.  
  
    -   En C\#, haga clic en la pestaña **Compilar** que se encuentra en el panel izquierdo de la página de propiedades. A continuación, seleccione las casillas correspondientes a los valores de configuración del compilador que desee habilitar.  Desactive las casillas de los valores de configuración que desee deshabilitar.  
  
### Para compilar código instrumentado desde la línea de comandos  
  
1.  Establezca un modificador de compilación condicional en la línea de comandos.  El compilador incluirá código de seguimiento o depuración en el archivo ejecutable.  
  
     Por ejemplo, la siguiente instrucción del compilador especificada en la línea de comandos incluiría el código de seguimiento en un ejecutable compilado:  
  
     En Visual Basic: **vbc \/r:System.dll \/d:TRACE\=TRUE \/d:DEBUG\=FALSE MiAplicación.vb**  
  
     En C\#: **csc \/r:System.dll \/d:TRACE \/d:DEBUG\=FALSE MiAplicación.cs**  
  
    > [!TIP]
    >  Para compilar varios archivos de aplicación, deje un espacio en blanco entre los nombres de archivo, por ejemplo, **MiAplicación1.vb MiAplicación2.vb MiAplicación3.vb** o **MiAplicación1.cs MiAplicación2.cs MiAplicación3.cs**.  
  
     El significado de las directivas de compilación condicional usadas en los ejemplos anteriores es el siguiente:  
  
    |Directiva|Significado|  
    |---------------|-----------------|  
    |`vbc`|compilador de Visual Basic|  
    |`csc`|Compilador de C\#|  
    |`/r:`|Hace referencia a un ensamblado externo \(EXE o DLL\)|  
    |`/d:`|Define un símbolo de compilación condicional|  
  
    > [!NOTE]
    >  TRACE o DEBUG deben escribirse en letras mayúsculas.  Para obtener más información sobre los comandos de compilación condicional, escriba `vbc /?` \(para Visual Basic\) o `csc /?` \(para C\#\) en el símbolo del sistema.  Para obtener más información, consulte los artículos sobre [compilación desde la línea de comandos](../Topic/How%20to:%20Set%20Environment%20Variables%20for%20the%20Visual%20Studio%20Command%20Line.md) \(C\#\) o [invocación del compilador de línea de comandos](../Topic/How%20to:%20Invoke%20the%20Command-Line%20Compiler%20\(Visual%20Basic\).md) \(Visual Basic\).  
  
### Para realizar compilación condicional mediante \#CONST o \#define  
  
1.  Escriba la instrucción apropiada para su lenguaje de programación en la parte superior del archivo de código fuente.  
  
    |Lenguaje|Instrucción|Resultado|  
    |--------------|-----------------|---------------|  
    |**Visual Basic**|**\#CONST TRACE \= true**|Habilita el seguimiento|  
    ||**\#CONST TRACE \= false**|Deshabilita el seguimiento|  
    ||**\#CONST DEBUG \= true**|Habilita la depuración|  
    ||**\#CONST DEBUG \= false**|Deshabilita la depuración|  
    |**C\#**|**\#define TRACE**|Habilita el seguimiento|  
    ||**\#undef TRACE**|Deshabilita el seguimiento|  
    ||**\#define DEBUG**|Habilita la depuración|  
    ||**\#undef DEBUG**|Deshabilita la depuración|  
  
### Para deshabilitar el seguimiento o la depuración  
  
1.  Elimine la directiva de compilador del código fuente.  
  
     o bien  
  
2.  Convierta en comentario la directiva de compilador.  
  
    > [!NOTE]
    >  Cuando esté preparado para compilar, puede elegir **Compilar** desde el menú **Compilar** o bien usar el método de línea de comandos, pero sin escribir **d:** para definir símbolos de compilación condicional.  
  
## Vea también  
 [Tracing and Instrumenting Applications](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)   
 [How to: Create, Initialize and Configure Trace Switches](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)   
 [Trace Switches](../../../docs/framework/debug-trace-profile/trace-switches.md)   
 [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md)   
 [How to: Add Trace Statements to Application Code](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)   
 [How to: Set Environment Variables for the Visual Studio Command Line](../Topic/How%20to:%20Set%20Environment%20Variables%20for%20the%20Visual%20Studio%20Command%20Line.md)   
 [Cómo: Invocar al compilador de la línea de comandos](../Topic/How%20to:%20Invoke%20the%20Command-Line%20Compiler%20\(Visual%20Basic\).md)