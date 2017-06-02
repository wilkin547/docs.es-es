---
title: "Dynamic Language Runtime Overview | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "dynamic language runtime"
  - "IronPython"
  - "DLR"
  - "IronRuby"
ms.assetid: f769a271-8aff-4bea-bfab-6160217ce23d
caps.latest.revision: 26
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 26
---
# Dynamic Language Runtime Overview
*Dynamic Language Runtime* \(DLR\) es un entorno en tiempo de ejecución que agrega un conjunto de servicios para lenguajes dinámicos a Common Language Runtime \(CLR\).  Con DLR es más fácil desarrollar lenguajes dinámicos para su ejecución en .NET Framework y agregar características dinámicas a lenguajes con tipos estáticos.  
  
 Los lenguajes dinámicos pueden identificar el tipo de un objeto en tiempo de ejecución, mientras que en los lenguajes con tipos estáticos como C\# y Visual Basic \(cuando se usa `Option Explicit On`\) debe especificar los tipos de los objetos en tiempo de diseño.  Algunos ejemplos de lenguajes dinámicos son Lisp, Smalltalk, JavaScript, PHP, Ruby, Python, ColdFusion, Lua, Cobra y Groovy.  
  
 La mayoría de los lenguajes dinámicos proporcionan las ventajas siguientes a los desarrolladores:  
  
-   Posibilidad de usar un bucle de comentarios rápido \(REPL o bucle de lectura\-evaluación\-impresión\).  Esto le permite escribir varias instrucciones y ejecutarlas inmediatamente para ver los resultados.  
  
-   Compatibilidad con el desarrollo descendente y el desarrollo ascendente más tradicional.  Por ejemplo, cuando usa un enfoque descendente, puede llamar a funciones que no se han implementado todavía y agregar implementaciones subyacentes cuando las necesite.  
  
-   Refactorización y modificaciones del código más sencillas, ya que no es necesario cambiar las declaraciones de tipos estáticas a lo largo del código.  
  
 Los lenguajes dinámicos son excelentes lenguajes de scripting.  Los clientes pueden extender fácilmente aplicaciones creadas mediante lenguajes dinámicos con nuevos comandos y nueva funcionalidad.  Los lenguajes dinámicos también se usan con frecuencia para crear sitios web y sistemas de prueba, mantener granjas de servidores, desarrollar diversas utilidades y realizar transformaciones de datos.  
  
 El propósito de DLR es permitir la ejecución de un sistema de lenguajes dinámicos en .NET Framework y aportarles interoperabilidad .NET.  DLR presenta objetos dinámicos en C\# y Visual Basic en Visual Studio 2010 para admitir el comportamiento dinámico en estos lenguajes y permitir su interoperación con lenguajes dinámicos.  
  
 DLR también le ayuda a crear bibliotecas que admiten operaciones dinámicas.  Por ejemplo, si tiene una biblioteca que usa objetos XML o Notación de objetos JavaScript \(JSON\), sus objetos pueden aparecer como objetos dinámicos en los lenguajes que usan DLR.  Esto permite a los usuarios de la biblioteca escribir código sintácticamente más sencillo y más natural para trabajar con objetos y obtener acceso a miembros de objetos.  
  
 Por ejemplo, podría usar el código siguiente para incrementar un contador en XML en C\#.  
  
 `Scriptobj.SetProperty("Count", ((int)GetProperty("Count")) + 1);`  
  
 Con DLR, podría usar en su lugar el código siguiente para realizar la misma operación.  
  
 `scriptobj.Count += 1;`  
  
 Al igual que CLR, DLR forma parte de .NET Framework y se proporciona con los paquetes de instalación de Visual Studio y .NET Framework.  La versión de Abrir\- origen de DLR también se puede descargar del [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141028) sitio Web.  
  
> [!NOTE]
>  La versión de código fuente abierto de DLR tiene todas las características de DLR incluidas en Visual Studio y en .NET Framework.  También proporciona compatibilidad adicional para implementadores de lenguaje.  Para obtener más información, vea la documentación del [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141028) sitio Web.  
  
 A continuación se indican algunos ejemplos de lenguajes desarrollados usando DLR:  
  
-   IronPython.  Disponible como software de Abrir\- origen [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141040) del sitio Web.  
  
-   IronRuby.  Disponible como software de Abrir\- origen [RubyForge](http://go.microsoft.com/fwlink/?LinkId=141044) del sitio Web.  
  
## Ventajas principales de DLR  
 DLR proporciona las ventajas siguientes.  
  
### Simplifica el traslado de lenguajes dinámicos a .NET Framework  
 DLR permite que los implementadores de lenguaje no tengan que crear analizadores léxicos, analizadores, analizadores semánticos, generadores de código y otras herramientas que tradicionalmente tenían que crear ellos mismos.  Para usar DLR, un lenguaje necesita generar *árboles de expresión*, que representan el código de nivel de lenguaje en una estructura en forma de árbol, rutinas auxiliares en tiempo de ejecución y objetos dinámicos opcionales que implementan la interfaz <xref:System.Dynamic.IDynamicMetaObjectProvider>.  DLR y .NET Framework automatizan muchas tareas de análisis y generación de código.  Esto permite a los implementadores de lenguaje concentrarse en características únicas del lenguaje.  
  
### Habilita características dinámicas en lenguajes con tipos estáticos  
 Los lenguajes .NET Framework existentes como C\# y Visual Basic puede crear objetos dinámicos y usarlos junto con objetos con tipos estáticos.  Por ejemplo, C\# y Visual Basic pueden usar objetos dinámicos para HTML, Modelo de objetos de documento \(DOM\) y reflexión de .NET.  
  
### Proporciona ventajas futuras de DLR y .NET Framework  
 Los lenguajes implementados mediante DLR pueden beneficiarse de futuras mejoras de DLR y .NET Framework.  Por ejemplo, si se publica una nueva versión de .NET Framework que tiene un recolector de elementos no utilizados mejorado o tiempos de carga de ensamblados más rápidos, los lenguajes implementados mediante DLR obtendrán inmediatamente esa misma ventaja.  Si DLR agrega optimizaciones como una mejor compilación, el rendimiento también mejorará para todos los lenguajes implementados mediante DLR.  
  
### Permite el uso compartido de bibliotecas y objetos  
 Otros lenguajes pueden usar los objetos y las bibliotecas implementados en un lenguaje.  DLR también permite la interoperación entre los lenguajes con tipos estáticos y los lenguajes dinámicos.  Por ejemplo, C\# puede declarar un objeto dinámico que usa una biblioteca escrita en un lenguaje dinámico.  Al mismo tiempo, los lenguajes dinámicos pueden usar bibliotecas de .NET Framework.  
  
### Proporciona envío dinámico e invocación rápidos  
 DLR permite la ejecución rápida de operaciones dinámicas admitiendo el almacenamiento en caché polimórfico avanzado.  DLR crea reglas para operaciones de enlace que usan objetos en las implementaciones en tiempo de ejecución necesarias y, a continuación, almacena en memoria caché estas reglas para evitar cálculos de enlace que agoten los recursos durante las ejecuciones sucesivas del mismo código en los mismos tipos de objetos.  
  
## Arquitectura de DLR  
 La ilustración siguiente muestra la arquitectura de Dynamic Language Runtime.  
  
 ![Información general sobre la arquitectura de Dynamic Language Runtime](../../../docs/framework/reflection-and-codedom/media/dlr-archoverview.png "DLR\_ArchOverview")  
Arquitectura de DLR  
  
 DLR agrega un conjunto de servicios al CLR para admitir mejor los lenguajes dinámicos.  Entre estos servicios se incluyen los siguientes:  
  
-   Árboles de expresión.  DLR usa árboles de expresión para representar la semántica del lenguaje.  Para ello, DLR ha extendido los árboles de expresión LINQ para incluir flujo de control, asignación y otros nodos de modelado del lenguaje.  Para obtener más información, vea [Árboles de expresión](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md).  
  
-   Almacenamiento en memoria caché de sitios de llamada.  Un *sitio de llamada dinámico* es un lugar del código donde realiza una operación como `a + b` o `a.b()` en objetos dinámicos.  DLR almacena en memoria caché las características de `a` y `b` \(normalmente los tipos de estos objetos\) e información sobre la operación.  Si previamente se ha realizado una operación de este tipo, DLR recupera toda la información necesaria de la memoria caché para su envío rápido.  
  
-   Interoperabilidad de objetos dinámicos.  DLR proporciona un conjunto de clases e interfaces que representan operaciones y objetos dinámicos, y que los implementadores de lenguaje y los autores de bibliotecas dinámicas pueden usar.  Estas clases e interfaces incluyen <xref:System.Dynamic.IDynamicMetaObjectProvider>, <xref:System.Dynamic.DynamicMetaObject>, <xref:System.Dynamic.DynamicObject> y <xref:System.Dynamic.ExpandoObject>.  
  
 DLR usa enlazadores en sitios de llamada para comunicarse no solo con .NET Framework, sino con otras infraestructuras y servicios, incluyendo Silverlight y COM.  Los enlazadores encapsulan la semántica de un lenguaje y especifican cómo realizar operaciones en un sitio de llamada usando árboles de expresión.  Esto permite que lenguajes dinámicos y con tipos estáticos que usan DLR compartan bibliotecas y obtengan acceso a todas las tecnologías compatibles con DLR.  
  
## Documentación DLR  
 Para obtener más información sobre cómo usar la versión de código fuente abierto de DLR para agregar comportamiento dinámico a un lenguaje, o acerca de cómo habilitar el uso de un lenguaje dinámico con .NET Framework, vea la documentación del [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141028) sitio Web.  
  
## Vea también  
 <xref:System.Dynamic.ExpandoObject>   
 <xref:System.Dynamic.DynamicObject>   
 [Common Language Runtime](../../../docs/standard/clr.md)   
 [Árboles de expresión](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)   
 [Tutorial: Crear y utilizar objetos dinámicos](../Topic/Walkthrough:%20Creating%20and%20Using%20Dynamic%20Objects%20\(C%23%20and%20Visual%20Basic\).md)