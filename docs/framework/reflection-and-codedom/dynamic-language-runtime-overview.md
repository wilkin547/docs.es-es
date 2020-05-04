---
title: Información general sobre Dynamic Language Runtime | Microsoft Docs
ms.date: 03/30/2017
helpviewer_keywords:
- dynamic language runtime
- IronPython
- DLR
- IronRuby
ms.assetid: f769a271-8aff-4bea-bfab-6160217ce23d
ms.openlocfilehash: a38ed15769d1186ef78733d68d9d8b51b3eb262d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446897"
---
# <a name="dynamic-language-runtime-overview"></a>Información general acerca de Dynamic Language Runtime

*Dynamic Language Runtime* (DLR) es un entorno en tiempo de ejecución que agrega un conjunto de servicios para lenguajes dinámicos en Common Language Runtime (CLR). DLR hace más fácil desarrollar lenguajes dinámicos para ejecutarlos en .NET Framework y agregar características dinámicas a lenguajes de tipos estáticos.

Los lenguajes dinámicos pueden identificar el tipo de un objeto en tiempo de ejecución, mientras que en los lenguajes de tipos estáticos, como C# y Visual Basic (cuando se usa `Option Explicit On`) es necesario especificar los tipos de objeto en tiempo de diseño. Entre los ejemplos de lenguajes dinámicos se incluyen Lisp, Smalltalk, JavaScript, PHP, Ruby, Python, ColdFusion, Lua, Cobra y Groovy.

La mayoría de los lenguajes dinámicos ofrece las siguientes ventajas a los desarrolladores:

- Capacidad de usar un bucle de comentarios rápido (bucle de lectura-evaluación-impresión o REPL). Esto permite escribir varias instrucciones y ejecutarlas inmediatamente para ver los resultados.

- Compatibilidad con el desarrollo de arriba abajo y el desarrollo más tradicional de abajo arriba. Por ejemplo, si usa un enfoque de arriba abajo, puede llamar a funciones que todavía no se han implementado y, después, agregar implementaciones subyacentes cuando las necesite.

- Refactorización y modificaciones de código más fáciles, ya que no es necesario cambiar las declaraciones de tipo estático en todo el código.

Los lenguajes dinámicos son excelentes lenguajes de scripting. Los clientes pueden extender fácilmente las aplicaciones creadas mediante lenguajes dinámicos con nuevos comandos y funcionalidades. Los lenguajes dinámicos también se suelen usar para crear sitios web y herramientas de ejecución de pruebas, mantener granjas de servidores, desarrollar diversas utilidades y realizar transformaciones de datos.

El propósito de DLR consiste en permitir que un sistema de lenguajes dinámicos se ejecute en .NET Framework y aportarles interoperabilidad .NET. DLR agrega objetos dinámicos en C# y Visual Basic para admitir el comportamiento dinámico en estos lenguajes y permitir su interoperabilidad con lenguajes dinámicos.

DLR también ayuda a crear bibliotecas que admiten operaciones dinámicas. Por ejemplo, si tiene una biblioteca que usa objetos XML o de notación de objetos JavaScript (JSON), los objetos pueden aparecer como objetos dinámicos en los lenguajes que usan DLR. Esto permite que los usuarios de la biblioteca escriban código sintácticamente más sencillo y más natural para trabajar con objetos y obtener acceso a miembros de objeto.

Por ejemplo, podría usar el código siguiente para incrementar un contador en XML en C#.

`Scriptobj.SetProperty("Count", ((int)GetProperty("Count")) + 1);`

Mediante el uso de DLR, podría usar el código siguiente en su lugar para la misma operación.

`scriptobj.Count += 1;`

Al igual que CLR, DLR forma parte de .NET Framework y se proporciona con los paquetes de instalación de .NET Framework y Visual Studio. La versión de código abierto de DLR también está disponible para su descarga en el repositorio [IronLanguages/dlr](https://github.com/IronLanguages/dlr) en GitHub.

> [!NOTE]
> La versión de código abierto de DLR tiene todas las características del DLR que se incluye en Visual Studio y .NET Framework. Además, proporciona compatibilidad adicional para implementadores del lenguaje. Para más información, vea la documentación en el repositorio [IronLanguages/dlr](https://github.com/IronLanguages/dlr) en GitHub.

Algunos ejemplos de lenguajes desarrollados con DLR son los siguientes:

- IronPython. Disponible como software de código abierto en el sitio web de [GitHub](https://github.com/IronLanguages/ironpython2).

- IronRuby. Disponible como software de código abierto en el sitio web de [IronRuby](http://ironruby.net/).

## <a name="primary-dlr-advantages"></a>Principales ventajas de DLR
 DLR ofrece las ventajas que se indican a continuación.

### <a name="simplifies-porting-dynamic-languages-to-the-net-framework"></a>Simplifica el traslado de lenguajes dinámicos a .NET Framework
 DLR evita a los implementadores del lenguaje crear analizadores léxicos, semánticos y de otro tipo, así como generadores de código y otras herramientas que tradicionalmente tenían que crear por sí mismos. Para usar DLR, un lenguaje debe generar *árboles de expresión*, que representan el código del nivel de lenguaje en una estructura en forma de árbol, rutinas del asistente en tiempo de ejecución y objetos dinámicos opcionales que implementan la interfaz <xref:System.Dynamic.IDynamicMetaObjectProvider>. DLR y .NET Framework automatizan muchas de las tareas de análisis de código y generación de código. Esto permite que los implementadores del lenguaje se concentren en características únicas del lenguaje.

### <a name="enables-dynamic-features-in-statically-typed-languages"></a>Habilita características dinámicas en lenguajes de tipos estáticos
 Los lenguajes de .NET Framework existentes, como C# y Visual Basic, pueden crear objetos dinámicos y usarlos con objetos de tipos estáticos. Por ejemplo, C# y Visual Basic pueden usar objetos dinámicos para la reflexión .NET, HTML y Document Object Model (DOM).

### <a name="provides-future-benefits-of-the-dlr-and-net-framework"></a>Proporciona las futuras ventajas de DLR y .NET Framework
 Los lenguajes implementados mediante DLR pueden beneficiarse de las mejoras futuras de DLR y .NET Framework. Por ejemplo, si .NET Framework lanza una nueva versión que tiene un recolector de elementos no utilizados mejorado o un tiempo de carga de ensamblados más rápido, los lenguajes implementados mediante DLR pueden beneficiarse de inmediato de dicha ventaja. Si DLR agrega optimizaciones como una mejor compilación, el rendimiento también mejora para todos los lenguajes implementados mediante DLR.

### <a name="enables-sharing-of-libraries-and-objects"></a>Habilita el uso compartido de bibliotecas y objetos
 Los objetos y las bibliotecas implementados en un lenguaje pueden usarlos otros lenguajes. DLR también permite la interoperabilidad entre los lenguajes de tipos estáticos y los lenguajes dinámicos. Por ejemplo, C# puede declarar un objeto dinámico que usa una biblioteca escrita en un lenguaje dinámico. Al mismo tiempo, los lenguajes dinámicos pueden usar bibliotecas de .NET Framework.

### <a name="provides-fast-dynamic-dispatch-and-invocation"></a>Proporciona una distribución y una invocación dinámicas rápidas
 DLR permite la ejecución rápida de operaciones dinámicas, ya que admite el almacenamiento en caché polimórfico avanzado. DLR crea reglas para operaciones de enlace que usan objetos en las implementaciones en tiempo de ejecución necesarias y, después, almacena en caché estas reglas para evitar los cálculos de enlace que agotan los recursos durante las ejecuciones sucesivas del mismo código en los mismos tipos de objetos.

## <a name="dlr-architecture"></a>Arquitectura de DLR
 En la ilustración siguiente se muestra la arquitectura de Dynamic Language Runtime.

 ![Información general sobre la arquitectura de Dynamic Language Runtime](./media/dlr-archoverview.png "DLR_ArchOverview") Arquitectura de DLR

 DLR agrega un conjunto de servicios a CLR para una mejor compatibilidad con los lenguajes dinámicos. Entre estos servicios, se incluyen los siguientes:

- Árboles de expresión. DLR usa árboles de expresión para representar la semántica del lenguaje. Para ello, DLR ha extendido los árboles de expresión LINQ de modo que incluyan el flujo de control, la asignación y otros nodos de modelado del lenguaje. Para más información, vea [Árboles de expresión (C#)](../../csharp/programming-guide/concepts/expression-trees/index.md) o [Árboles de expresión (Visual Basic)](../../visual-basic/programming-guide/concepts/expression-trees/index.md).

- Almacenamiento en caché del sitio de llamada. Un *sitio de llamada dinámico* es un lugar del código donde se realiza una operación como `a + b` o `a.b()` en objetos dinámicos. DLR almacena en caché las características de `a` y `b` (generalmente, los tipos de estos objetos) e información sobre la operación. Si ya se ha realizado previamente una operación de este tipo, DLR recupera toda la información necesaria de la memoria caché para su distribución rápida.

- Interoperabilidad de objetos dinámicos. DLR proporciona un conjunto de clases e interfaces que representan operaciones y objetos dinámicos que pueden usar los implementadores del lenguaje y los autores de bibliotecas dinámicas. Entre estas clases e interfaces se incluyen <xref:System.Dynamic.IDynamicMetaObjectProvider>, <xref:System.Dynamic.DynamicMetaObject>, <xref:System.Dynamic.DynamicObject> y <xref:System.Dynamic.ExpandoObject>.

DLR usa enlazadores en los sitios de llamada para comunicarse no solo con .NET Framework, sino con otras infraestructuras y servicios, incluidos Silverlight y COM. Los enlazadores encapsulan la semántica de un lenguaje y especifican cómo se realizan las operaciones en un sitio de llamada mediante el uso de árboles de expresión. Esto permite que los lenguajes dinámicos y de tipos estáticos que usan DLR compartan bibliotecas y obtengan acceso a todas las tecnologías que admite DLR.

## <a name="dlr-documentation"></a>Documentación de DLR
 Para más información sobre cómo usar la versión de código abierto de DLR para agregar comportamiento dinámico a un lenguaje o sobre cómo habilitar el uso de un lenguaje dinámico con .NET Framework, vea la documentación en el repositorio [IronLanguages/dlr](https://github.com/IronLanguages/dlr/tree/master/Docs) en GitHub.

## <a name="see-also"></a>Vea también

- <xref:System.Dynamic.ExpandoObject>
- <xref:System.Dynamic.DynamicObject>
- [Common Language Runtime](../../standard/clr.md)
- [Árboles de expresión (C#)](../../csharp/programming-guide/concepts/expression-trees/index.md)
- [Árboles de expresión (Visual Basic)](../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [Tutorial: Crear y usar objetos dinámicos](../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
